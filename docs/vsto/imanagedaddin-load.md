---
title: IManagedAddin::Load | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d6c657698f0d0e3a10871a7276a4eac2617d7874
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  Volá se při načtení spravované Add-in VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Load([in] BSTR bstrManifestURL,   
             [in] IDispatch *pdispApplication);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*bstrManifestURL*|Úplná cesta manifestu pro doplňku VSTO.|  
|*pdispApplication*|Ukazatel IDispatch, který představuje hostitelskou aplikaci, která je načítání doplňku VSTO.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Manifest je soubor (obvykle soubor XML), který poskytuje informace, které se používají pro načtení doplňku VSTO. Manifest můžete například zadat umístění doplňku VSTO sestavení a třída vstupní bod pro vytvoření instance při načítání doplňku VSTO.  
  
 *BstrManifestURL* parametr obsahuje hodnotu `Manifest` položky v rámci HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<název aplikace >*\Addins\\*\<ID doplněk >* klíč registru pro doplňku VSTO. Další informace najdete v tématu [imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md).  
  
 Implementace [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) metoda k provádění úloh, jako je například konfigurace zásad domény a zabezpečení aplikací pro VSTO doplněk, který je právě načítán.  
  
## <a name="see-also"></a>Viz také  
 [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
  
  