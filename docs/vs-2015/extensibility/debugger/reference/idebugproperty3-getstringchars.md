---
title: IDebugProperty3::GetStringChars | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 661cf6833c292d5ff4015649d494ee3a7d04fdbb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419887"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte řetězec přidružený k této vlastnosti a ukládá ho do uživatelem zadané vyrovnávací paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `buflen`  
 [in] Maximální počet znaků, které může obsahovat uživatelem zadané vyrovnávací paměti.  
  
 `rgString`  
 [out] Vrátí řetězec.  
  
 [C++ pouze], `rgString` je ukazatel do vyrovnávací paměti, která přijímá znaků Unicode řetězce. Tuto vyrovnávací paměť musí být dlouhý aspoň `buflen` znaků (ne v bajtech) velikosti.  
  
 `pceltFetched`  
 [out] Pokud se vrátí počet znaků ve skutečnosti uloženy ve vyrovnávací paměti. (Může být `NULL` v jazyce C++.)  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V jazyce C++, musí věnovat pozornost – pomáhat zajistit, že vyrovnávací paměť je alespoň `buflen` znaků Unicode. Všimněte si, že znak Unicode je 2 bajty dlouhý.  
  
> [!NOTE]
> Vrácený řetězec v jazyce C++, nezahrnuje ukončující znak null. Pokud tento parametr zadaný, `pceltFetched` určí počet znaků v řetězci.  
  
## <a name="example"></a>Příklad  
<!-- TODO: review snippet reference  [!CODE [[cpp]]([cpp])]  -->  
  
```  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);  
```  
  
<!-- TODO: review snippet reference  [!CODE [}](})]  -->  
  
## <a name="see-also"></a>Viz také  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)