---
title: IDebugModule3::GetSymbolInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule3::GetSymbolInfo
helpviewer_keywords:
- GetSymbolInfo method
- IDebugModule3::GetSymbolInfo method
ms.assetid: dda5e8e1-6878-4aa9-9ee4-e7d0dcc11210
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8648e591e545db73b636c6b21fcbcaa1d1afb640
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmodule3getsymbolinfo"></a>IDebugModule3::GetSymbolInfo
Načte seznam cest, které budou prohledávány pro symboly, jakož i výsledky hledání každá cesta.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetSymbolInfo(  
   SYMBOL_SEARCH_INFO_FIELDS  dwFields,  
   MODULE_SYMBOL_SEARCH_INFO* pInfo  
);  
```  
  
```csharp  
int GetSymbolInfo(  
   enum_SYMBOL_SEARCH_INFO_FIELDS dwFields,   
   MODULE_SYMBOL_SEARCH_INFO[]    pinfo  
);  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFields`  
 [v] Kombinace příznaků z [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) výčtu zadání polí s `pInfo` mají být vyplněna.  
  
 `pInfo`  
 [out] A [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md) struktura, jejíž členové jsou pro vyplnění zadané informace. Pokud je to hodnota null, vrátí tato metoda `E_INVALIDARG`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda bude úspěšná, vrátí `S_OK`, jinak vrátí kód chyby.  
  
> [!NOTE]
>  Vrácený řetězec (v `MODULE_SYMBOL_SEARCH_INFO` struktura) může být prázdný i v případě `S_OK` je vrácen. V takovém případě se žádné informace o hledání vrátit.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `bstrVerboseSearchInfo` pole z `MODULE_SYMBOL_SEARCH_INFO` struktura není prázdný a obsahuje seznam cest vyhledávat a výsledky vyhledávání. V seznamu je naformátován s cestou, za nímž následuje třemi tečkami ("..."), za nímž následuje výsledek. Pokud existuje více než jednu dvojici výsledek cestu, každý pár jsou oddělené oddělovačem pár "\r\n" (znaků CR vrátit/konce řádku). Vzor vypadá takto:  
  
 \<cesta >... \<výsledek > \r\n\<cesta >... \<výsledek > \r\n\<cesta >... \<výsledek >  
  
 Všimněte si, že poslední položka nemá \r\n pořadí.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu tato metoda vrátí tři cesty s tři různé výsledky hledání. Každý řádek je byla ukončena s pár znaků CR vrátit/konce řádku. Příklad výstupu právě vytiskne výsledky hledání jako jeden řetězec.  
  
> [!NOTE]
>  Stav výsledek je všechno hned za "..." až do konce řádku.  
  
```cpp  
void ShowSymbolSearchResults(IDebugModule3 *pIDebugModule3)  
{  
    MODULE_SYMBOL_SEARCH_INFO ssi = { 0 };  
    HRESULT hr;  
    hr = pIDebugModule3->GetSymbolInfo(SSIF_VERBOSE_SEARCH_INFO,&ssi);  
    if (SUCCEEDED(hr)) {  
        CComBSTR searchInfo = ssi.bstrVerboseSearchInfo;  
        if (searchInfo.Length() != 0) {  
            std::wcout << (wchar_t *)(BSTR)searchInfo;  
            std::wcout << std::endl;  
        }  
    }  
}  
```  
  
 **c:\symbols\user32.pdb... Soubor nebyl nalezen.**  
**c:\winnt\symbols\user32.pdb... Verze neodpovídá.**  
**\\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symboly načíst.**   
## <a name="see-also"></a>Viz také  
 [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md)   
 [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md)   
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)