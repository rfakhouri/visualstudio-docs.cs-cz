---
title: IDebugDocumentHelper::AddDeferredText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDeferredText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDeferredText
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2f2a7c134142668613cc38cee9357e42cb95096
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63433932"
---
# <a name="idebugdocumenthelperadddeferredtext"></a>IDebugDocumentHelper::AddDeferredText
Pomocná rutina upozorní, že daný text je k dispozici, ale neposkytuje znaky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cChars`  
 [in] Počet znaků (Unicode) Chcete-li přidat.  
  
 `dwTextStartCookie`  
 [in] Hostitel definované souboru cookie, který představuje počáteční pozici textu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Metoda se nezdařila.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda umožňuje hostiteli odložit poskytuje znaky, které chcete přidat, dokud nejsou potřeba, přičemž pomocné rutiny pro generování přesné oznámení a informace o velikosti. `dwTextStartCookie` Parametr je soubor cookie, určené hostitele, který představuje počáteční pozici textu. Následující volání `IDebugDocumentText::GetText` musíte zadat Tento soubor cookie. Například v hostiteli, který reprezentuje text v DBCS, může být soubor cookie bajtovým posunem.  
  
 Předpokládá se, že jediné volání `IDebugDocumentText::GetText` můžete získat znaky z více volání `AddDeferredText`. Pomocné třídy mohou také požádat o stejný rozsah znaků odložené více než jednou.  
  
> [!NOTE]
> Volání `AddDeferredText` by neměl být směšovat s voláními `AddUnicodeText` nebo `AddDBCSText`. Pokud k tomu dojde, `E_FAIL` je vrácena.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHelper Interface](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)