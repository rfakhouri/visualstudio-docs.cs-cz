---
title: "Příkaz implementace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, implementation
ms.assetid: c782175c-cce4-4bd0-8374-4a897ceb1b3d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2704794e4683fb461dca971a3893ca831591ca0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-implementation"></a>Příkaz implementace
Chcete-li implementovat příkaz ve VSPackage, musíte provést následující úlohy:  
  
1.  V souboru .vsct nastavte skupinu příkaz a potom k němu přidejte příkaz. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
2.  Příkaz zaregistrujte pomocí sady Visual Studio.  
  
3.  Implementujte příkaz.  
  
 Následující části popisují způsob registrace a implementovat příkazy.  
  
## <a name="registering-commands-with-visual-studio"></a>Registrace příkazy pomocí sady Visual Studio  
 Pokud je váš příkaz zobrazit v nabídce, je nutné přidat <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> VSPackage a použít jako hodnotu buď název nabídky, nebo jeho ID prostředku.  
  
```  
[ProvideMenuResource("Menus.ctmenu", 1)]  
...  
    public sealed class MyPackage : Package  
    {.. ..}  
  
```  
  
 Kromě toho je nutné zaregistrovat příkaz se <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService>. Tuto službu můžete získat pomocí <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metoda Pokud vaše VSPackage je odvozený od <xref:Microsoft.VisualStudio.Shell.Package>.  
  
```  
OleMenuCommandService mcs = GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
if ( null != mcs )  
{  
    // Create the command for the menu item.  
    CommandID menuCommandID = new CommandID(guidCommandGroup, myCommandID);  
    MenuCommand menuItem = new MenuCommand(MenuItemCallback, menuCommandID );  
    mcs.AddCommand( menuItem );  
}  
  
```  
  
## <a name="implementing-commands"></a>Implementace příkazy  
 Existuje několik způsobů, jak implementovat příkazy. Statické nabídky příkaz, který je příkaz, který se vždy zobrazí stejný způsobem a v nabídce stejné, chcete-li vytvořit pomocí příkazu <xref:System.ComponentModel.Design.MenuCommand> jak je znázorněno v příkladech v předchozí části. Chcete-li vytvořit statickou příkaz, je nutné zadat obslužnou rutinu události, která je odpovědná za provádění příkazu. Vzhledem k tomu, že příkaz je vždycky povolená a viditelné, nemáte poskytují jeho stav v sadě Visual Studio. Pokud chcete změnit stav příkazu v závislosti na určité podmínky, můžete vytvořit příkaz jako jedna instance <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> třídy a v jeho konstruktoru, zadejte obslužné rutiny události provedení příkazu a zjistit stav obslužná rutina oznámit Visual Studio, když se změní stav příkazu. Můžete taky implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> jako součást třídu příkazu nebo je můžete implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> poskytujete příkaz v rámci projektu. Tato dvě rozhraní a <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> všechny třídy mají metody, které Visual Studio změny ve stavu příkazu a jiné metody, které poskytují provedení příkazu.  
  
 Pokud příkaz se na službu příkaz přidá, bude řetězec příkazy. Pokud implementujete stav oznámení a provádění metody pro příkaz, vezměte v potaz, zadejte pouze pro tuto konkrétní příkazu a předávat všech ostatních případech k jiné příkazy v řetězu. Pokud se nepodaří předat příkaz na (obvykle vrácením <xref:Microsoft.VisualStudio.OLE.Interop.Constants>), Visual Studio může přestane fungovat správně.  
  
## <a name="query-status-methods"></a>Metody stav dotazů  
 Pokud implementujete buď <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> metoda, kontrola identifikátoru GUID sadu, ke které patří příkaz příkazů a ID příkazu. Postupujte podle následujících pokynů:  
  
-   Pokud není rozpoznán identifikátor GUID, musí vracet vaší implementace metody <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
-   Pokud vaše implementace metody rozpozná identifikátor GUID, ale ve skutečnosti neimplementovala příkaz, pak metoda by měla vrátit <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
-   Pokud vaše implementace metody rozpozná identifikátor GUID a příkaz, pak metoda by měla nastavte hodnotu pole příkaz příznaky každých příkazu (v `prgCmds` parametr) pomocí následující příznaky:  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud je příkaz podporována.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud příkaz by neměly být viditelné.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud příkaz zdá být ověřeno a je zapnutá.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud je povoleno příkaz.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud příkaz by být skrytý, pokud se zobrazí v místní nabídce.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>Pokud příkaz nabídky řadiče a není povolena, ale jeho seznamu rozevírací nabídky není prázdné a je stále k dispozici. (Tento příznak se používá zřídka.)  
  
-   Pokud byl příkaz definované v souboru .vsct s `TextChanges` příznak, nastavte následující parametry:  
  
    -   Nastavte `rgwz` element `pCmdText` parametr na nový text příkazu.  
  
    -   Nastavit `cwActual` element `pCmdText` parametr velikosti text příkazu.  
  
 Ujistěte se také, aktuálním kontextu není funkcí automatizace, pokud příkazu je určený speciálně pro zpracování funkce automatizace.  
  
 K označení, že podporujete konkrétní příkaz, vrátí <xref:Microsoft.VisualStudio.VSConstants.S_OK>. U všech ostatních příkazů vrátit <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
 V následujícím příkladu metoda dotazu stav nejprve zajišťuje, že kontextu není funkcí automatizace a potom vyhledá správný identifikátor GUID sadu příkazů a ID příkazu. Samotný příkaz nastavena na povolena a podporované. Jsou podporovány žádné další příkazy.  
  
```  
public int QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.VSStd2K && cCmds > 0)  
        {  
            // make the Right command visible   
            if ((uint)prgCmds[0].cmdID == (uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                prgCmds[0].cmdf = (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_ENABLED | (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_SUPPORTED;  
                return VSConstants.S_OK;  
            }  
        }  
        return Constants.OLECMDERR_E_NOTSUPPORTED;  
    }  
}  
  
```  
  
## <a name="execution-methods"></a>Spuštění metody  
 Implementace metody spouštění vypadá takto: implementace metody stav dotazu. Nejprve zkontrolujte, zda kontext není funkcí automatizace. Proveďte testujte pro identifikátor GUID a ID příkazu. Pokud identifikátor GUID nebo ID příkazu, který nebyl rozpoznán, vraťte se <xref:Microsoft.VisualStudio.OLE.Interop.Constants>.  
  
 Pro zpracování příkazu, provést a vrátit <xref:Microsoft.VisualStudio.VSConstants.S_OK> -li spuštění úspěšné. Váš příkaz zodpovídá za detekce chyb a oznámení; proto vrátí kód chyby, pokud se nezdaří spuštění. Následující příklad ukazuje, jak by měla být implementována metoda spuštění.  
  
```  
public int Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.GUID_VSStandardCommandSet97)  
        {  
             if (nCmdID ==(uint) uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                //execute the command  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    return Constants.OLECMDERR_E_NOTSUPPORTED;  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)