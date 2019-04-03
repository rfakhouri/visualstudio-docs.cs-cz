---
title: IDispatchEx::GetNextDispID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNextDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNextDispID method
ms.assetid: 8263d441-85ee-47f4-bdba-fbf2ad07e85f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d964a8744f1f0a28704dd0a1d5e0fd2e67aab1c
ms.sourcegitcommit: 05d104a14ff357d599ff274f97cd59d464ee4a46
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2019
ms.locfileid: "58897670"
---
# <a name="idispatchexgetnextdispid"></a>IDispatchEx::GetNextDispID

Vytvoří výčet členy objektu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetNextDispID(
   DWORD grfdex,
   DISPID id,
   DISPID *pid
);
```

## <a name="parameters"></a>Parametry

`grfdex`\
Určuje, které sadu položek vytvořit výčet. To může být kombinací následujícího:

|Hodnota|Význam|
|-----------|-------------|
|fdexEnumDefault|Požadavky, že objekt vytvoří výčet výchozími prvky. Objekt může vytvořit výčet všech sadu elementů.|
|fdexEnumAll|Požadavky, že objekt vytvoří výčet všech prvků. Objekt může vytvořit výčet všech sadu elementů.|

`id`\
Identifikuje aktuálního člena. Getnextdispid – načte položku ve výčtu po tomto požadavku. Getdispid – nebo předchozí volání getnextdispid – používá k získání tento identifikátor. Použije se hodnota DISPID_STARTENUM získat první identifikátor první položky.

`pid`\
Adresa proměnné DISPID, která přijímá identifikátor na další položku ve výčtu.

Pokud je člen odstraní `DeleteMemberByName` nebo `DeleteMemberByDispID`, `DISPID` jsou dál platné pro je potřeba `GetNextDispID`.

## <a name="return-value"></a>Návratová hodnota

Vrátí jednu z následujících hodnot:

|||
|-|-|
|`S_OK`|Úspěch.|
|`S_FALSE`|Výčet je Hotovo.|

## <a name="example"></a>Příklad

```cpp
   HRESULT hr;
   BSTR bstrName;
   DISPID dispid;
   IDispatchEx *pdex;

   // Assign to pdex
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);
   while (hr == NOERROR)
   {
      hr = pdex->GetMemberName(dispid, &bstrName);
      if (!wcscmp(bstrName, OLESTR("Bar")))
      {
         SysFreeString(bstrName);
         return TRUE;
      }
      SysFreeString(bstrName);
      hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);
   }
```

## <a name="see-also"></a>Viz také:

- [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)
- [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)
- [IDispatchEx::DeleteMemberByName](../../winscript/reference/idispatchex-deletememberbyname.md)
- [IDispatchEx::DeleteMemberByDispID](../../winscript/reference/idispatchex-deletememberbydispid.md)