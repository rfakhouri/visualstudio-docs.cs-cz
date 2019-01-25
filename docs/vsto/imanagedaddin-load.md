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
ms.openlocfilehash: 267e2ec1b2ec2dbb5b72a100185ce6b68d455c39
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865880"
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
 [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
