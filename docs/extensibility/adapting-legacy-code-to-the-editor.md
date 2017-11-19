---
title: "Přizpůsobení starší verze kódu do editoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - adapters
ms.assetid: a208d38e-9bea-41c9-9fe2-38bd86a359cb
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 03c0cbd20258618297e943524d06ba7b3a496264
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adapting-legacy-code-to-the-editor"></a>Přizpůsobení starší verze kódu do editoru
Editoru Visual Studio obsahuje řadu funkcí, které je přístupné z existující kód součásti. Následující pokyny ukazují, jak přizpůsobit bez MEF součásti, například VSPackage, využívat funkce editor. Podle pokynů také ukazují, jak použít adaptéry získání služby editoru ve spravovaných i nespravovaných kódu.  
  
## <a name="editor-adapters"></a>Editor adaptéry  
 Editor adaptéry nebo překrytí, jsou obálek pro editor objektů, které také poskytují třídy a rozhraní <xref:Microsoft.VisualStudio.TextManager.Interop> rozhraní API. Můžete použít adaptéry, aby přesunout mezi službami jiný editor, například příkazy prostředí sady Visual Studio a editor služby. (To je, jak se aktuálně hostuje editoru v sadě Visual Studio.) Adaptéry také povolit starší verze editoru a jazyk rozšíření služeb fungovat správně v sadě Visual Studio.  
  
## <a name="using-editor-adapters"></a>Použití adaptérů editoru  
 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> Poskytuje metody, které přepínat mezi nové rozhraní editoru a starší verze rozhraní a metody, které vytvářejí adaptéry.  
  
 Používáte-li tato služba součást MEF, můžete službu importovat následujícím způsobem.  
  
```  
[Import(typeof(IVsEditorAdaptersFactoryService))]  
internal IVsEditorAdaptersFactoryService editorFactory;  
```  
  
 Pokud chcete tuto službu využívat v komponentě rozhraní MEF, postupujte podle pokynů v části "Použití Visual Studio Editor služby v Non-MEF Component" dále v tomto tématu.  
  
## <a name="switching-between-the-new-editor-api-and-the-legacy-api"></a>Přepínání mezi nového editoru rozhraní API a rozhraní API starší verze  
 Použijte následující metody pro přepínání z editoru objektu a starší verze rozhraní.  
  
|Metoda|Převod|  
|------------|----------------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetBufferAdapter%2A>|Převede <xref:Microsoft.VisualStudio.Text.ITextBuffer> k <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDataBuffer%2A>|Převede <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> k <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDocumentBuffer%2A>|Převede <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> k <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetViewAdapter%2A>|Převede <xref:Microsoft.VisualStudio.Text.Editor.ITextView> k <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetWpfTextView%2A>|Převede <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> k <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>.|  
  
## <a name="creating-adapters"></a>Vytváření adaptérů  
 Použijte následující metody pro vytvoření adaptéry pro starší verze rozhraní.  
  
|Metoda|Převod|  
|------------|----------------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsCodeWindowAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> pro zadané <xref:Microsoft.VisualStudio.Utilities.IContentType>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferCoordinatorAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> pro <xref:Microsoft.VisualStudio.Text.Editor.ITextViewRoleSet>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|Vytvoří <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
  
## <a name="creating-adapters-in-unmanaged-code"></a>Vytváření adaptérů v nespravovaném kódu  
 Všechny třídy adaptér je zaregistrovaný být místní společně vytvořitelné a může být vytvořena pomocí `VsLocalCreateInstance()` funkce.  
  
 Všechny adaptéry se vytváří pomocí identifikátory GUID, které jsou definovány v souboru vsshlids.h ve... Složka \VisualStudioIntegration\Common\Inc\ instalace Visual Studio SDK. Pokud chcete vytvořit instanci VsTextBufferAdapter, použijte následující kód.  
  
```  
IVsTextBuffer *pBuf = NULL;  
VsLocalCreateInstance(CLSID_VsTextBuffer, NULL, CLSCTX_INPROC_SERVER, IID_IVsTextBuffer, (void**)&pBuf);  
```  
  
## <a name="creating-adapters-in-managed-code"></a>Vytváření adaptérů ve spravovaném kódu  
 Ve spravovaném kódu můžete současně vytvořit adaptéry stejným způsobem, jako je popsán pro nespravovaného kódu. Můžete taky MEF služba, která umožňuje vytvářet a interakci s adaptéry. Tento způsob získání adaptér umožňuje jemněji odstupňované řízení než máte, když vytvoříte společně.  
  
#### <a name="to-create-an-adapter-for-ivstextview"></a>Chcete-li vytvořit adaptér pro IVsTextView  
  
1.  Přidáte odkaz na Microsoft.VisualStudio.Editor.dll. Ujistěte se, že `CopyLocal` je nastaven na `false`.  
  
2.  Vytvoření instance <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>, a to takto.  
  
    ```  
    using Microsoft.VisualStudio.Editor;  
    ...  
    IVsEditorAdaptersFactoryService adapterFactoryService = ComponentModel.GetService<IVsEditorAdaptersFactoryService>();  
    ```  
  
3.  Volání `CreateX()` metoda.  
  
    ```  
    adapterFactoryService.CreateTextViewAdapter(textView);  
    ```  
  
## <a name="using-the-visual-studio-editor-directly-from-unmanaged-code"></a>Pomocí editoru Visual Studio přímo z nespravovaného kódu  
 Obor názvů Microsoft.VisualStudio.Platform.VSEditor a obor názvů Microsoft.VisualStudio.Platform.VSEditor.Interop vystavit volatelná aplikacemi COM rozhraní v IVx * rozhraní. Například rozhraní Microsoft.VisualStudio.Platform.VSEditor.Interop.IVxTextBuffer je verze modelu COM <xref:Microsoft.VisualStudio.Text.ITextBuffer> rozhraní. Z `IVxTextBuffer`, můžete získat přístup k snímky vyrovnávací paměti, upravit vyrovnávací paměti, naslouchání událostem změny textu ve vyrovnávací paměti a vytvořte body sledování a rozpětí. Následující kroky ukazují, jak získat přístup `IVxTextBuffer` z `IVsTextBuffer`.  
  
#### <a name="to-get-an-ivxtextbuffer"></a>Chcete-li získat IVxTextBuffer  
  
1.  Definice rozhraní IVx * se v souboru VSEditor.h ve... Složka \VisualStudioIntegration\Common\Inc\ instalace Visual Studio SDK.  
  
2.  Následující kód vytvoří textové vyrovnávací paměti pomocí `IVsUserData->GetData()` metoda. V následujícím kódu `pData` je ukazatel na `IVsUserData` objektu.  
  
    ```  
    #include <textmgr.h>  
    #include <VSEditor.h>  
    #include <vsshlids.h>  
  
    CComPtr<IVsTextBuffer> pVsTextBuffer;  
    CComPtr<IVsUserData> pData;  
    CComPtr<IVxTextBuffer> pVxBuffer;  
    ...  
    if (SUCCEEDED(pVsTextBuffer->QueryInterface(IID_IVsUserData, &pData))  
    {  
        CComVariant vt;  
        if (SUCCEEDED(pData->GetData(GUID_VxTextBuffer, &vt)) &&  
        (vt.Type == VT_UNKNOWN) && (vt.punkVal != NULL))  
        {  
            vt.punkVal->QueryInterface(IID_IVxTextBuffer, (void**)&pVxBuffer);  
        }  
    }  
    ```  
  
## <a name="using-visual-studio-editor-services-in-a-non-mef-component"></a>Pomocí editoru Visual Studio služby v komponentě rozhraní MEF  
 Pokud máte existující součást spravovaného kódu, který nepoužívá MEF a chcete používat službu editoru Visual Studio, je nutné přidat odkaz na sestavení, které obsahuje ComponentModelHost VSPackage a získat jeho SComponentModel služby.  
  
#### <a name="to-consume-visual-studio-editor-components-from-a-non-mef-component"></a>Využívat součásti editoru Visual Studio pro součást rozhraní MEF  
  
1.  Přidat odkaz na sestavení Microsoft.VisualStudio.ComponentModelHost.dll v... Složka \Common7\IDE\ instalace Visual Studia. Ujistěte se, že `CopyLocal` je nastaven na `false`.  
  
2.  Přidat privátního `IComponentModel` člena třídy, ve které chcete použít editor služby Visual Studio, následujícím způsobem.  
  
    ```  
    using Microsoft.VisualStudio.ComponentModelHost;  
    ....  
    private IComponentModel componentModel;  
    ```  
  
3.  Vytvoří instanci modelu součásti v metodě inicializace pro příslušné součásti.  
  
    ```  
    componentModel =  
     (IComponentModel)Package.GetGlobalService(typeof(SComponentModel));  
    ```  
  
4.  Poté můžete získat kterákoli ze služeb editor Visual Studio voláním `IComponentModel.GetService<T>()` metoda pro službu chcete.  
  
    ```  
    textBufferFactoryService =  
         componentModel.GetService<ITextBufferFactoryService>();     
    ```