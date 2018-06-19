---
title: Vytvoření okna nástroj s více instancemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 910ca8f223d5f4f37242990ba7384afb0dbebd7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31097793"
---
# <a name="creating-a-multi-instance-tool-window"></a>Vytvoření okna nástroj s více instancemi
Okno nástroje můžete naprogramovat tak, aby více instancí může být otevřena současně. Ve výchozím nastavení nástroj windows může mít pouze jednu instanci otevřete.  
  
 Pokud použijete nástroj okno s více instancemi, můžete zobrazit několik související zdroje informací ve stejnou dobu. Můžete například zadat více řádků <xref:System.Windows.Forms.TextBox> tak, aby několik fragmenty kódu jsou současně dostupné během relace programovací řízení v okně nástroje s více instancemi. Například může taky <xref:System.Windows.Forms.DataGrid> řízení a rozevíracího seznamu pole v okně nástroje s více instancemi tak, aby několik zdrojů dat v reálném čase lze sledovat současně.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Vytvoření okna Nástroj Basic (Single-Instance)  
  
1.  Vytvoření projektu s názvem **MultiInstanceToolWindow** pomocí VSIX šablony a přidat vlastní nástroj šablonu položky okno s názvem **MIToolWindow**.  
  
    > [!NOTE]
    >  Další informace o vytváření rozšíření s okno nástroje najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="making-a-tool-window-multi-instance"></a>Provedení nástroj s více instancemi okna  
  
1.  Otevřete **MIToolWindowPackage.cs** souboru a najděte `ProvideToolWindow` atribut. a `MultiInstances=true` parametr, jak je znázorněno v následujícím příkladu:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackage.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  V souboru MIToolWindowCommand.cs nalezena metoda ShowToolWindos(). Tato metoda volání <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> metoda a sadu jeho `create` příznak, který `false` tak, aby se iterace existující instance okno nástroj dokud dostupný `id` nenajde.  
  
3.  Chcete-li vytvořit instanci okno nástroj, volejte <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> metoda a sadu jeho `id` na k dispozici hodnotu a jeho `create` příznak, který `true`.  
  
     Výchozí hodnota `id` parametr <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> je metoda `0`. Tato hodnota je okno nástroj jedné instance. Pro více než jednu instanci pro hostování každé instance musí mít svůj vlastní jedinečný `id`.  
  
4.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metodu <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekt, který je vrácen <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> vlastnost instance okno nástroje.  
  
5.  Ve výchozím nastavení `ShowToolWindow` metoda, který je vytvořen pomocí šablony položky okno nástroj vytvoří okno nástroj jedné instance. Následující příklad ukazuje, jak upravit `ShowToolWindow` metodu pro vytvoření více instancí.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```