---
title: 如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 9957eae7e15c99ec259574b435402420c6bcf5f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页
Windows 窗体<xref:System.Windows.Forms.LinkLabel>控制可以在你的窗体上创建 Web 样式的链接。 单击该链接后，你可以更改其颜色来表示访问链接。 将颜色更改的详细信息，请参阅[如何： 更改 Windows 窗体 LinkLabel 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)。  
  
## <a name="linking-to-another-form"></a>将链接到另一个窗体  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>若要链接到另一个窗体 LinkLabel 控件  
  
1.  设置<xref:System.Windows.Forms.LinkLabel.Text%2A>为适当标题的属性。  
  
2.  设置<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性来确定哪个部分的标题将指示的链接的形式。 指示方式取决于的链接标签的外观相关的属性。 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>表示值<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>对象，其中包含两个数字、 起始字符位置和字符数。 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性可以在属性窗口或在代码中的方式类似于以下设置：  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  在<xref:System.Windows.Forms.LinkLabel.LinkClicked>事件处理程序调用<xref:System.Windows.Forms.Form.Show%2A>方法以在项目中，打开另一个窗体，并设置<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性`true`。  
  
    > [!NOTE]
    >  实例<xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs>类执行的引用<xref:System.Windows.Forms.LinkLabel>控件被单击，因此不需要强制转换`sender`对象。  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a>将链接到网页  
 <xref:System.Windows.Forms.LinkLabel>控件还可以用于显示具有默认浏览器的 Web 页。  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>若要使用 LinkLabel 控件启动 Internet Explorer 并链接到网页  
  
1.  设置<xref:System.Windows.Forms.LinkLabel.Text%2A>为适当标题的属性。  
  
2.  设置<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性来确定哪个部分的标题将指示的链接的形式。  
  
3.  在<xref:System.Windows.Forms.LinkLabel.LinkClicked>事件处理程序，在过程中的异常处理块中，调用设置的第二个过程<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性`true`并使用<xref:System.Diagnostics.Process.Start%2A>方法以提供一个 URL 启动默认浏览器。 若要使用<xref:System.Diagnostics.Process.Start%2A>方法需要添加对引用<xref:System.Diagnostics?displayProperty=nameWithType>命名空间。  
  
    > [!IMPORTANT]
    >  如果在部分信任环境中运行下面的代码 (如共享驱动器上)，JIT 编译器失败时`VisitLink`调用方法。 `System.Diagnostics.Process.Start`语句会导致失败的链接要求。 通过捕获异常时`VisitLink`方法被调用时，下面的代码可确保如果 JIT 编译器失败，适当地处理错误。  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>  
 [LinkLabel 控件概述](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [如何：更改 Windows 窗体 LinkLabel 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)  
 [LinkLabel 控件](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
