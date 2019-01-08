---
title: IDebugDocumentHelper::DefineScriptBlock | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.DefineScriptBlock
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::DefineScriptBlock
ms.assetid: e4120377-f04f-44b1-950b-2beba06c9c12
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0037df270bc95faaba4d2f04cce65902d08dc6e9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087994"
---
# <a name="idebugdocumenthelperdefinescriptblock"></a>IDebugDocumentHelper::DefineScriptBlock
Signalizuje možnost do pomocné rutiny určitého rozsahu znaků blok skriptu, který zařizuje služba dané skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT DefineScriptBlock(  
   ULONG           ulCharOffset,  
   ULONG           cChars,  
   IActiveScript*  pas,  
   BOOL            fScriptlet,  
   DWORD_PTR*      pdwSourceContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ulCharOffset`  
 [in] Umístění začátku bloku skriptu.  
  
 `cChars`  
 [in] Počet znaků v bloku skriptu.  
  
 `pas`  
 [in] Skriptovací stroj pro daný blok skriptu.  
  
 `fScriptlet`  
 [in] Příznak, který určuje, zda je blok skriptu skriptletu.  
  
 `pdwSourceContext`  
 [out] Místní zdroje v bloku skriptu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Inteligentního hostitele lze tuto metodu použijte, když svoje dokumenty obsahují bloků vloženého skriptu. Tuto metodu můžete použít modul jazyka, když jeho kód obsahuje vložené skripty pro jiné jazyky.  
  
 Skriptovací stroj je zodpovědná za všechny syntaxe barevné zvýrazňování a kód místní vyhledávání v bloku skriptu.  
  
 `DefineScriptBlock` Metoda by měla být volána po přidání text (například pomocí `IDebugDocumentHelper::AddDBCSText` metoda), ale před skript má být blok (například pomocí `IActiveScriptParse ::ParseScriptText` – metoda).  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenthelper – rozhraní](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)