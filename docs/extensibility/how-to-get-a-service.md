---
title: 'Postupy: získání služby | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, consuming
ms.assetid: 1f000020-8fb7-4e39-8e1e-2e38c7fec3d4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cdf5bd925a034a64d8605c675704a0e894308ea3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132453"
---
# <a name="how-to-get-a-service"></a>Postupy: získání služby
Často je potřeba získat sady Visual Studio službám přístup k různých funkcí. Obecně platí služby Visual Studio poskytuje jeden nebo více rozhraní, které můžete použít. Většina služeb můžete získat z VSPackage.  
  
 Všechny VSPackage, která je odvozena z <xref:Microsoft.VisualStudio.Shell.Package> a který správně umístěný můžete požádat o žádné globální služby. Protože třída balíčku implementuje <xref:System.IServiceProvider>, všechny VSPackage, která je odvozena z balíčku je také poskytovatele služeb.  
  
 Když se načte Visual Studio <xref:Microsoft.VisualStudio.Shell.Package>, předává <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> do objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> metoda během inicializace. To se označuje jako *umístění* VSPackage. Třída balíčku zabalí tuto poskytovatele služeb a poskytuje <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metodu než služeb.  
  
## <a name="getting-a-service-from-an-initialized-vspackage"></a>Získávání služby z inicializovaného VSPackage  
  
1.  Každé rozšíření sady Visual Studio začíná projekt nasazení VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projektu s názvem `GetServiceExtension`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# > rozšíření**.  
  
2.  Nyní přidejte šablonu a vlastní příkaz položka s názvem **GetServiceCommand**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# > rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **GetServiceCommand.cs**. Další informace o tom, jak vytvořit vlastní příkaz [vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
3.  V GetServiceCommand.cs odeberte těla metody MenuItemCommand a přidejte následující kód:  
  
    ```csharp  
    IVsActivityLog activityLog = ServiceProvider.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (activityLog == null) return;  
    System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
  
    ```  
  
     Tento kód získá služby SVsActivityLog a obsahuje ji do <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní, které lze použít k zápisu do protokolu činnosti. Příklad, naleznete v části [postupy: použití protokolu činnosti](../extensibility/how-to-use-the-activity-log.md).  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
5.  V nabídce Nástroje pro experimentální instance najít **vyvolání GetServiceCommand** tlačítko. Po kliknutí na toto tlačítko, měli byste vidět okno se zprávou, která uvádí, že **nalezen služby protokolování aktivity.**  
  
## <a name="getting-a-service-from-a-tool-window-or-control-container"></a>Získávání z nástroj okno nebo řízení kontejneru služby  
 Někdy může musíte získat službu z okna nástroje nebo řízení kontejneru, který nebyl byla umístěný, jinak má byla umístěný s poskytovatelem služby, který nebude vědět o službu, kterou chcete. Například můžete chtít zapisovat do protokolu aktivit z v rámci ovládacího prvku.  
  
 Statické <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda je založena na uložené v mezipaměti služby zprostředkovatele, který je inicializován poprvé žádné VSPackage odvozené z <xref:Microsoft.VisualStudio.Shell.Package> je umístěný.  
  
 Protože volání konstruktoru VSPackage předtím, než je umístěný VSPackage, jsou obvykle ze není k dispozici v rámci konstruktoru VSPackage služeb global services. V tématu [postupy: řešení potíží s služby](../extensibility/how-to-troubleshoot-services.md) alternativní řešení.  
  
 Tady je příklad toho, jak získat služby v okně nástroje nebo jiného bez VSPackage elementu.  
  
```csharp  
IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
## <a name="getting-a-service-from-the-dte-object"></a>Získávání služby z objektu DTE  
 Můžete také získat služby od <xref:EnvDTE.DTEClass> objektu. Však musíte získat objekt DTE jako služby z VSPackage nebo voláním statické <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda.  
  
 Implementuje objekt DTE <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, který můžete použít k dotazu pro službu pomocí <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>.  
  
 Chcete-li získat službu z prostředí DTE objektu.  
  
```csharp  
// Start with the DTE object, for example:   
// using EnvDTE;  
// DTE dte = (DTE)GetService(typeof(DTE));  
  
ServiceProvider sp = new ServiceProvider((Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
if (sp != null)  
{  
    IVsActivityLog log = sp.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log != null)  
    {   
        System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: poskytování služby](../extensibility/how-to-provide-a-service.md)   
 [Použití a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Základy služeb](../extensibility/internals/service-essentials.md)