---
title: "基于 Roslyn 的分析器 - .NET"
description: "了解基于 Roslyn 的分析器，用其发现问题并针对这些问题提供修复建议。"
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="99c1a-104">基于 Roslyn 的分析器</span><span class="sxs-lookup"><span data-stu-id="99c1a-104">The Roslyn based Analyzers</span></span>

<span data-ttu-id="99c1a-105">基于 Roslyn 的分析器使用 .NET Compiler SDK (Roslyn Api) 来分析项目源代码，以找到问题并提供更正建议。</span><span class="sxs-lookup"><span data-stu-id="99c1a-105">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="99c1a-106">不同分析器寻找不同种类的问题，范围从有可能导致 bug 的做法到有关 API 兼容性的安全问题。</span><span class="sxs-lookup"><span data-stu-id="99c1a-106">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="99c1a-107">基于 Roslyn 的分析器以交互方式工作并在生成期间运行。</span><span class="sxs-lookup"><span data-stu-id="99c1a-107">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="99c1a-108">分析器将在 Visual Studio 或命令行生成过程中提供不同的指导。</span><span class="sxs-lookup"><span data-stu-id="99c1a-108">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="99c1a-109">当你在 Visual Studio 中编辑代码时，分析器会在你进行更改时运行，一旦创建触发问题的代码，它便会捕获可能存在的问题。</span><span class="sxs-lookup"><span data-stu-id="99c1a-109">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="99c1a-110">对于任何问题，均会在其下用波浪线进行突出显示。</span><span class="sxs-lookup"><span data-stu-id="99c1a-110">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="99c1a-111">Visual Studio 会显示一个灯泡，单击它时，分析器将针对该问题给出可能的修复建议。</span><span class="sxs-lookup"><span data-stu-id="99c1a-111">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="99c1a-112">生成项目时，将在 Visual Studio 中或通过命令行分析所有源代码，并且分析器会提供潜在问题的完整列表。</span><span class="sxs-lookup"><span data-stu-id="99c1a-112">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="99c1a-113">下图显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="99c1a-113">The following figure shows one example.</span></span>

![框架分析器报告的问题](./media/framework-analyzers-2.png)

<span data-ttu-id="99c1a-115">基于 Roslyn 的分析器会报告潜在问题，如错误、警告或基于问题严重程度的信息。</span><span class="sxs-lookup"><span data-stu-id="99c1a-115">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="99c1a-116">在项目中，可以将基于 Roslyn 的分析器作为 NuGet 包进行安装。</span><span class="sxs-lookup"><span data-stu-id="99c1a-116">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="99c1a-117">已配置的分析器以及每个分析器的任何设置都将恢复，并在该项目任何开发人员的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="99c1a-117">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="99c1a-118">基于 Roslyn 的分析器的用户体验与旧版本的 FxCop 和安全分析工具等代码分析库的用户体验不同。</span><span class="sxs-lookup"><span data-stu-id="99c1a-118">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="99c1a-119">你不必显式运行基于 Roslyn 的分析器。</span><span class="sxs-lookup"><span data-stu-id="99c1a-119">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="99c1a-120">无需在 Visual Studio 的“分析”菜单上使用“运行代码分析”菜单项。</span><span class="sxs-lookup"><span data-stu-id="99c1a-120">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="99c1a-121">基于 Roslyn 的分析器会在你工作时异步运行。</span><span class="sxs-lookup"><span data-stu-id="99c1a-121">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="99c1a-122">有关特定分析器的详细信息</span><span class="sxs-lookup"><span data-stu-id="99c1a-122">More information on specific analyzers</span></span>

<span data-ttu-id="99c1a-123">本部分中将介绍以下分析器：</span><span class="sxs-lookup"><span data-stu-id="99c1a-123">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="99c1a-124">[API 分析器](api-analyzer.md)：此分析器检查代码是否存在潜在的兼容性风险，或者是否使用了弃用的 API。</span><span class="sxs-lookup"><span data-stu-id="99c1a-124">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="99c1a-125">[框架分析器](framework-analyzer.md)：此分析器对代码进行检查，确保它遵循 .NET Framework 应用程序的准则。</span><span class="sxs-lookup"><span data-stu-id="99c1a-125">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="99c1a-126">这些规则包括多个基于安全的建议。</span><span class="sxs-lookup"><span data-stu-id="99c1a-126">These rules include several security-based recommendations.</span></span>