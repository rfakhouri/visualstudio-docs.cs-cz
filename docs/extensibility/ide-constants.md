---
title: Konstanty IDE | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e9c7e870b02dbe5a903ca8195954ffd5a8f63549
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133096"
---
# <a name="ide-constants"></a>Konstanty IDE

<xref:Microsoft.VisualStudio.VSConstants> Třída obsahuje konstanty, které jsou specifické pro integrované vývojové prostředí (IDE) a které byly dříve definovány pouze v záhlaví souboru.

## <a name="logical-and-physical-views"></a>Logické a fyzické zobrazení

|Hodnota|Popis|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny musí předat tuto hodnotu na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda získat **otevřít v** dialogové okno, v tomto případě na možné zobrazení kódu.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny předat tuto hodnotu na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda získat **otevřít v** dialogové okno, v takovém případě naplněný možné <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid> ladění zobrazení, které mapování na stejné zobrazení jako <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Designer_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny předat tuto hodnotu na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda získat **otevřít v** dialogové okno, v tomto případě k **zobrazit formulář** návrháře zobrazení.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Primary_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny předat tuto hodnotu na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda získat **otevřít v** dialogové okno, v tomto případě výchozí/primární zobrazení objekt factory editoru.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.TextView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny předat tuto hodnotu na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda získat **otevřít v** dialogové okno, v tomto zobrazení editoru textu dokumentu nebo data.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.UserChooseView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` obslužné rutiny předat této hodnoty <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metodu, která vyzývá uživatele k vyberte zobrazení, které uživatelem definované používat.|

## <a name="editor-factory-flags"></a>Příznaky Factory editoru

|Hodnota|Popis|
|-----------|-----------------|
|[CEF. CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>)|Zastaralé příznak kombinaci bitový jako první parametr <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> metoda.|
|[CEF.OpenAsNew](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenAsNew>)|Bitový jako první parametr kombinaci <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>, metoda, to znamená objekt factory editoru proveďte potřebné opravy.|
|[CEF.OpenFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenFile>)|Bitový jako první parametr kombinaci <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> metoda, tento příznak je vzájemně exclusive [CEF. CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>).|
|[CEF. Tichou](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_Silent>)|Kombinaci bitový jako první parametr <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> metoda, to znamená objekt factory editoru měli vytvořit editoru bez zobrazení uživatelského rozhraní (UI).|

## <a name="visual-studio-errors"></a>Chyby v sadě Visual Studio

|Hodnota|Popis|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|Konstanta vrácený rozhraní asynchronní chování při v objektu již zaneprázdněných|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro "nekompatibilní dokumentu data".|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "Balíček není načtená."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a která informuje, že "Projektu již existuje."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "konfigurace projektu se nezdařilo."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "Projektu není načtená."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "Řešení už je otevřená."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "Řešení není otevřené."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|Vrácený pomocí sestavení rozhraní, které mají parametry pro zadání pole z <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> rozhraní, ale implementace lze použít pouze metodu pro všechny výstupy.|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Metoda vrací hodnotu této, jestli má dokument formátu, který nelze otevřít v editoru.|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|Hodnotou HRESULT, která určuje, že uživatel klepněte na tlačítko Zpět v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] průvodce.|

## <a name="visual-studio-constants"></a>Konstanty v sadě Visual Studio

|Hodnota|Popis|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|K chybě HRESULT, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a určující "Projektu předávaných."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|Konstanta, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro "sady nástrojů značku."|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|Konstanta, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro všesměrové vysílání zprávy oznámení prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> metodu, která označuje začátek podobu činnosti.|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|Konstanta, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro všesměrové vysílání zprávy oznámení prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> metoda, která označuje konec podobu činnosti.|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|Konstanta, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro všesměrové vysílání zprávy oznámení prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> metoda, která určuje, že došlo ke změně metriky příkazového řádku.|
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|Konstanta, která je specifická pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] určující, že soubor cookie nebyl nastaven.|
|[VSITEMID.Nil](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Nil>)|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] identifikátor položky, který představuje chybí položka projektu. Tato hodnota se používá, pokud není aktuální výběr.|
|[VSITEMID. Kořenové](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] identifikátor položky, která představuje nejnižší úrovni hierarchie projektu a slouží k identifikaci celou hierarchii, a jednu položku.|
|[VSITEMID. Výběr](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Selection>)|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] identifikátor položky, která představuje aktuálně vybrané položky nebo položky, které mohou zahrnovat kořenem hierarchie.|

## <a name="ivsselectionevents"></a>IVsSelectionEvents
 Popisuje, jaké součásti rozhraní IDE právě byla vybrána, v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> , například volání.

|Konstanta|Hodnota|
|--------------|-----------|
|[SelectionElement.DocumentFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_DocumentFrame>)|0x2|
|[SelectionElement.PropertyBrowserSID](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_PropertyBrowserSID>)|0x4|
|[SelectionElement.StartupProject](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_StartupProject>)|0x3|
|[SelectionElement.UndoManager](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UndoManager>)|0x0|
|[SelectionElement.UserContext](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UserContext>)|0x5|
|[SelectionElement.WindowFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_WindowFrame>)|0x1|

## <a name="vsselelemid"></a>VSSELELEMID
 Konstanty slouží k určení, nový stav výběru.

|Konstanta|Hodnota|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1|

## <a name="component-selector-dialog-constants"></a>Konstanty dialogové okno pro výběr součástí

|Konstanta|Hodnota|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1 280|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER +. 1281|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER +. 1290|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER +. 1287|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER +. 1285|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289|

## <a name="see-also"></a>Viz také

- [Příkazy definované prostředím IDE pro rozšíření systémů projektů](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)