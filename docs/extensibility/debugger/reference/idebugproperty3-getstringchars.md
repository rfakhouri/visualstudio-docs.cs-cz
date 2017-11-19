---
title: IDebugProperty3::GetStringChars | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty3::GetStringChars
helpviewer_keywords: IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2bf3dbc9e7c2696e51dfb86b8aa1c62b5f940655
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
Načte řetězce spojeného s touto vlastností a ukládá je do vyrovnávací paměti zadanou uživatelem.  
  
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
 [v] Maximální počet znaků, které mohou být uloženy uživatelem zadané vyrovnávací paměti.  
  
 `rgString`  
 [out] Vrátí řetězec.  
  
 [C++ pouze], `rgString` ukazatel do vyrovnávací paměti, která přijímá znaky Unicode řetězce. Této vyrovnávací paměti musí být minimálně `buflen` znaků (ne v bajtech). velikost.  
  
 `pceltFetched`  
 [out] Kde se vrátí počet znaků, které jsou ve skutečnosti uložené ve vyrovnávací paměti. (Může být `NULL` v jazyce C++.)  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V jazyce C++ musí dát pozor zajistit, že vyrovnávací paměť je alespoň `buflen` znaků Unicode. Všimněte si, že znak Unicode 2 dlouho bajty.  
  
> [!NOTE]
>  V jazyce C++ vrácený řetězec neobsahuje ukončovací znak hodnoty null. Pokud je zadána `pceltFetched` bude určete počet znaků v řetězci.  
  
## <a name="example"></a>Příklad  
 
```cpp  
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
}
```    
  
## <a name="see-also"></a>Viz také  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)