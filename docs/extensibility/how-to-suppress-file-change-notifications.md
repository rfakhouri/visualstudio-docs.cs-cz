---
title: 'Postupy: potlačení upozornění o změně souboru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - suppress file change notification
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95821baec7f2f46a65e2ab0f0b0b78b0e397f2ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-suppress-file-change-notifications"></a>Postupy: potlačení upozornění o změně souboru
Po fyzický soubor představující textová vyrovnávací paměť se zobrazí dialogové okno se zprávou **chcete uložit změny do následující položky?** To se označuje jako oznámení o změně souboru. Pokud mnoho změn nebudou mít k souboru, ale toto dialogové okno zobrazení opakovaně může být brzy obtěžující.  
  
 Toto dialogové okno pomocí následujícího postupu můžete potlačit prostřednictvím kódu programu. Díky tomu můžete znovu načíst soubor okamžitě bez nutnosti výzvu k uložení změn pokaždé, když.  
  
### <a name="to-suppress-file-change-notification"></a>Potlačit upozornění na změnu souboru  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> metoda určit který objekt vyrovnávací paměti text k otevření souboru.  
  
2.  Přímé <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt, který je v paměti ignorovat sledování změn souborů prostřednictvím provedeného <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objektu (data dokumentu) a pak implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> metoda s `fIgnore` parametr Nastavte na `true`.  
  
3.  Volání metody na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní aktualizace v paměťově <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt s změny souborů (například pokud je pole do příslušné součásti).  
  
4.  Aktualizujte soubor na disku se změnami, bez ohledu na všechny čekající úpravy, které uživatel může mít v průběhu.  
  
     Tímto způsobem při přímé <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> upozornění na změnu objektu k obnovení monitorování pro soubor, textovou vyrovnávací paměť v paměti odráží změny, které jste vygenerovali, a také všechny neuložené úpravy. Odráží nejnovější kód vygenerovaný je soubor na disku a všechny dříve uložili změny uživatelem v uživatele upravit kód.  
  
5.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> metoda upozornit <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt k obnovení monitorování pro oznámení o změně souborů nastavením `fIgnore` parametru `false`.  
  
6.  Pokud budete chtít provést několik změn v souboru, jako v případě správy zdrojového kódu (SCC), se musí zjistit službu globální soubor změnu dočasně pozastavit oznámení o změně souboru.  
  
     Například pokud přepisování souboru a poté změňte časové razítko, musí pozastavit, oznámení o změně souborů, protože operace přepisování a timestample, každý se počítají jako samostatný soubor události změny. Chcete-li povolit oznámení o změně globální souboru místo toho by měly volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> metoda.  
  
## <a name="example"></a>Příklad  
 Následující ukazuje, jak potlačit oznámení o změně souboru.  
  
```cpp  
//Misc. helper classes  
  
CSuspendFileChanges::CSuspendFileChanges(  
    /* [in] */ const CString& strMkDocument,   
    /* [in] */ BOOL fSuspendNow /* = TRUE */)   
:  
    m_strMkDocument(strMkDocument),  
    m_fFileChangeSuspended(FALSE)  
{  
    if(fSuspendNow)  
        Suspend();  
}  
CSuspendFileChanges::~CSuspendFileChanges()  
{  
    Resume();  
}  
void CSuspendFileChanges::Suspend()  
{  
    USES_CONVERSION;  
  
    // Prevent suspend from suspending more than once.  
    if(m_fFileChangeSuspended)  
        return;  
  
    IVsRunningDocumentTable* pRDT =   
      _VxModule.GetIVsRunningDocumentTable();  
    ASSERT(pRDT);  
    if (!pRDT)  
        return;  
  
    CComPtr<IUnknown> srpDocData;  
    VSCOOKIE vscookie = VSCOOKIE_NIL;  
    pRDT->FindAndLockDocument(RDT_NoLock, T2COLE(m_strMkDocument),    
      NULL, NULL, &srpDocData, &vscookie);  
    if ( (vscookie == VSCOOKIE_NIL) || !srpDocData)  
        return;  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
    {  
        m_fFileChangeSuspended = TRUE;  
        srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, TRUE);   
        srpDocData->QueryInterface(IID_IVsDocDataFileChangeControl,   
          (void**)&m_srpIVsDocDataFileChangeControl);  
        if(m_srpIVsDocDataFileChangeControl)  
            m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(TRUE);  
    }  
}  
void CSuspendFileChanges::Resume()  
{  
    if(!m_fFileChangeSuspended)  
        return;  
  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
  
    srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, FALSE);   
    if(m_srpIVsDocDataFileChangeControl)  
        m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(FALSE);  
    m_fFileChangeSuspended = FALSE;  
    m_srpIVsDocDataFileChangeControl.Release();  
}  
// Misc. helper classes  
```  
  
## <a name="robust-programming"></a>Robustní programování  
 Pokud váš případ zahrnuje několik změn v souboru, jako v případě SCC, je potřeba obnovit oznámení o změně globální souborů před výstrahou dokumentu data k obnovení monitorování pro změny souborů.