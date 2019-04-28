---
title: IDebugDisassemblyStream2::GetDocument | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetDocument
helpviewer_keywords:
- IDebugDisassemblyStream2::GetDocument
ms.assetid: 3d039a44-ebaa-4413-ac18-7cfd92c408bd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cfc50f104c5fc942794c2e421f5aee508662ea3b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921702"
---
# <a name="idebugdisassemblystream2getdocument"></a>IDebugDisassemblyStream2::GetDocument
Získá zdrojový dokument přidružený k této vstupního datového proudu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDocument( 
   BSTR              bstrDocumentUrl,
   IDebugDocument2** ppDocument
);
```

```csharp
int GetDocument( 
   string              bstrDocumentUrl,
   out IDebugDocument2 ppDocument
);
```

#### <a name="parameters"></a>Parametry
 `bstrDocumentUrl`

 [in] Adresa URL dokumentu.

 `ppDocument`

 [out] Vrátí [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) objekt představující dokumentu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je implementována pomocí ladicími stroji, které mají textové dokumenty, které nejsou uloženy v souboru aplikace skutečný.

## <a name="see-also"></a>Viz také
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)