---
title: IManagedAddin::Load
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords: ''
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 87fb34e90d36383f49b6369fb1dea4b9854c7300
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604004"
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  Volá se, když je načten spravovaného doplňku VSTO.

## <a name="syntax"></a>Syntaxe

```csharp
HRESULT Load([in] BSTR bstrManifestURL,
             [in] IDispatch *pdispApplication);
```

### <a name="parameters"></a>Parametry

|Parametr|Popis|
|---------------|-----------------|
|*bstrManifestURL*|Úplná cesta manifest doplňku VSTO.|
|*pdispApplication*|Ukazatel na rozhraní IDispatch, který představuje hostitelská aplikace, který je právě načítán doplňku VSTO.|

## <a name="return-value"></a>Návratová hodnota
 Hodnota HRESULT, která označuje, zda metoda byla úspěšně dokončena.

## <a name="remarks"></a>Poznámky
 Manifest je soubor (obvykle soubor XML), který poskytuje informace, které slouží k načtení doplňku VSTO. Manifest můžete například zadat umístění sestavení doplňku VSTO a třída vstupní bod pro vytvoření instance při načtení doplňku VSTO.

 *BstrManifestURL* parametru obsahuje hodnotu `Manifest` položku **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<název aplikace >_ \Addins\\_\<ID doplňku >_**  klíč registru pro doplňku VSTO. Další informace najdete v tématu [imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md).

 Implementace [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) metoda k provádění úloh, jako je například konfigurace zásad aplikací domény a zabezpečení pro VSTO doplněk, který se načítá.

## <a name="see-also"></a>Viz také:
- [IManagedAddin – rozhraní](../vsto/imanagedaddin-interface.md)
- [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)
