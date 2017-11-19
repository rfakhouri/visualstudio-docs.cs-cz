---
title: "Postupy: registrace typů souborů Editor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - register file types
ms.assetid: 54846779-8290-48de-90ab-81011559d9a5
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9f2837dff6c5dd62c03da2ab340fca287a1da56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-register-editor-file-types"></a>Postupy: registrace Editor typů souborů
Nejjednodušší způsob, jak zaregistrovat editor typů souborů je pomocí atributy registrace zadaný jako součást [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] spravované třídy balíčků framework (MPF). Při implementaci vašeho balíčku v nativní [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], je také možné zapsat skript registru, který se zaregistruje jako editor a přidružené rozšíření.  
  
## <a name="registration-using-mpf-classes"></a>Registrace pomocí sady MPF třídy  
  
#### <a name="to-register-editor-file-types-using-mpf-classes"></a>K registraci editor typů souborů použijte sady MPF třídy  
  
1.  Zadejte <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> třídy s příslušnými parametry pro vaše editor ve třídě vaší VSPackage.  
  
    ```  
    [Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute(typeof(EditorFactory), ".Sample", 32,   
         ProjectGuid = "{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}",   
         TemplateDir = "..\\..\\Templates",   
         NameResourceID = 106)]  
    ```  
  
     Kde ". Ukázka"je rozšíření, které je registrované pro tohoto editoru a"32"je její úroveň priority.  
  
     `projectGuid` Je identifikátor GUID pro soubor různé typy, definované v <xref:Microsoft.VisualStudio.VSConstants.CLSID_MiscellaneousFilesProject>. Typ různé souboru zajišťuje, aby výsledný soubor není má být součástí procesu sestavení.  
  
     `TemplateDir`představuje složku obsahující soubory šablony, které jsou součástí ukázka spravované základní editor.  
  
     `NameResourceID`je definován v souboru Resources.h BasicEditorUI projektu a identifikuje editoru jako "Moje Editor".  
  
2.  Přepsání <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
     V implementaci <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda, volání <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> metoda a předejte jí instanci vaše objekt factory editoru jako ukázáno níže.  
  
    ```  
    protected override void Initialize()  
    {  
        Trace.WriteLine (string.Format(CultureInfo.CurrentCulture,   
        "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
           //Create Editor Factory  
        editorFactory = new EditorFactory(this);  
        base.RegisterEditorFactory(editorFactory);  
    }  
    ```  
  
     Tento krok zaregistruje objekt factory editoru a přípony souborů editor.  
  
3.  Zrušte registraci objekty Factory editoru.  
  
     Objekty Factory editoru jsou automaticky registrace, když VSPackage je zveřejněn. Pokud objekt factory editoru implementuje <xref:System.IDisposable> rozhraní, jeho `Dispose` metoda je volána poté, co má objekt factory odregistrován s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="registration-using-a-registry-script"></a>Registrace pomocí skriptu registru  
 Registrace objektů Factory editoru a typy souborů v nativní [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] se provádí pomocí skriptu registru zapsat do registru systému windows, které jsou popsány v následující.  
  
#### <a name="to-register-editor-file-types-using-a-registry-script"></a>K registraci editor typů souborů použijte skript registru  
  
1.  Ve vašem skriptu registru definovat objekt factory editoru a objekt factory editoru GUID řetězec jak je uvedeno v `GUID_BscEditorFactory` části následující skript registru. Navíc definujte rozšíření a prioritu pro rozšíření editoru:  
  
    ```  
  
          NoRemove Editors     {         %GUID_BscEditorFactory% = s 'RTF Editor'         {             val Package = s '%CLSID_Package%'             val DisplayName = s 'An RTF Editor'             val ExcludeDefTextEditor = d 1             val AcceptBinaryFiles = d 0  
  
            LogicalViews  
            {  
                val %LOGVIEWID_TextView% = s ''  
            }  
  
            OpenWithEntries  
            {  
            }  
  
            Extensions            {                val rtf = d 50            }  
        }  
    }  
    ```  
  
     Přípona souboru editor v tomto příkladu je označený jako ".rtf" a "50" je jeho prioritu. Identifikátor GUID řetězce jsou definovány v souboru Resource.h BscEdit ukázkový projekt.  
  
2.  Zaregistrujte VSPackage.  
  
3.  Zaregistrujte objekt factory editoru.  
  
     Objekt factory editoru je zaregistrován v <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> implementace.  
  
    ```  
    // create editor factory.  
    if (m_srpEdFact == NULL)   
    {  
        CComObject<CBscEditorFactory> *pEdFact = new CComObject<CBscEditorFactory>;  
        if (NULL == pEdFact)  
          return E_OUTOFMEMORY;  
  
        if (!pEdFact->FInit(this))  
          return E_UNEXPECTED;  
  
        m_srpEdFact = (IVsEditorFactory *) pEdFact;    // Note: assignment to a smart pointer does an AddRef()  
    }  
    // Query service for IVsRegisterEditors, register the editor factory  
    CComPtr<IVsRegisterEditors> srpRegEd;  
    if ((SUCCEEDED(m_srpPkgSiteSP->QueryService(SID_SVsRegisterEditors, IID_IVsRegisterEditors,(void **)&srpRegEd ))) && (srpRegEd != NULL))  
      {  
        ATLTRACE(TEXT(">> CVsPackage, registering editor factory.\n"));  
          if (FAILED(srpRegEd->RegisterEditor(GUID_BscEditorFactory,  
                      m_srpEdFact, &m_dwEditorCookie)))   
          {  
             ATLTRACE(TEXT(">> CVsPackage, RegisterEditor() failed.\n"));  
            return E_FAIL;  
          }  
      }  
        return S_OK;  
    }  
    ```  
  
     GUID řetězce jsou definovány v souboru Resource.h BscEdit projektu.