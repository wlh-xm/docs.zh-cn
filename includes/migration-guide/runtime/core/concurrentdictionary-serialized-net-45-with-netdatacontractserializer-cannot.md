### <a name="a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a><span data-ttu-id="fcd82-101">在 .NET 4.5 中使用 NetDataContractSerializer 序列化的 ConcurrentDictionary 无法通过 .NET 4.5.1 或 4.5.2 反序列化</span><span class="sxs-lookup"><span data-stu-id="fcd82-101">A ConcurrentDictionary serialized in .NET 4.5 with NetDataContractSerializer cannot be deserialized by .NET 4.5.1 or 4.5.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fcd82-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="fcd82-102">Details</span></span>|<span data-ttu-id="fcd82-103">由于对类型作了内部更改，因此在 .NET Framework 4.5 中使用 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> 序列化的 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象无法在 .NET Framework 4.5.1 或 .NET Framework 4.5.2 中反序列化。注意，反之则可行（可以通过 .NET Framework 4.5.x 序列化，然后通过 .NET Framework 4.5 反序列化）。</span><span class="sxs-lookup"><span data-stu-id="fcd82-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="fcd82-104">同样，使用 .NET Framework 4.6 可以实现所有 4.x 的跨版本序列化，单个版本的 .NET Framework 的序列化和反序列化不受影响。</span><span class="sxs-lookup"><span data-stu-id="fcd82-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>|
|<span data-ttu-id="fcd82-105">建议</span><span class="sxs-lookup"><span data-stu-id="fcd82-105">Suggestion</span></span>|<span data-ttu-id="fcd82-106">如果必须在 .NET Framework 4.5 和 .NET Framework 4.5.1/4.5.2 之间序列化和反序列化 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>，则应使用备用序列化程序（例如 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> 或 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> 序列化程序）而不是 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>。或者，由于此问题已在 .NET Framework 4.6 中解决，因此升级件到该版本的 .NET Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="fcd82-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="fcd82-107">范围</span><span class="sxs-lookup"><span data-stu-id="fcd82-107">Scope</span></span>|<span data-ttu-id="fcd82-108">次要</span><span class="sxs-lookup"><span data-stu-id="fcd82-108">Minor</span></span>|
|<span data-ttu-id="fcd82-109">版本</span><span class="sxs-lookup"><span data-stu-id="fcd82-109">Version</span></span>|<span data-ttu-id="fcd82-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="fcd82-110">4.5.1</span></span>|
|<span data-ttu-id="fcd82-111">类型</span><span class="sxs-lookup"><span data-stu-id="fcd82-111">Type</span></span>|<span data-ttu-id="fcd82-112">运行时</span><span class="sxs-lookup"><span data-stu-id="fcd82-112">Runtime</span></span>|
