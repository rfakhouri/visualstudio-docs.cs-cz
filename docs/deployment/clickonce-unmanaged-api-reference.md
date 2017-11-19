---
title: "Nespravovaná referenční dokumentace rozhraní API ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: "6"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 11e10800ff51abd6f95447d85204a44f8367f551
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="clickonce-unmanaged-api-reference"></a>Referenční dokumentace nespravovaného rozhraní API ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Nespravovaná veřejné rozhraní API z dfshim.dll.  
  
## <a name="cleanonlineappcache"></a>CleanOnlineAppCache zapne  
 Čistí nebo odinstaluje všechny online aplikace z [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] mezipaměť aplikací.  
  
### <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; Vrátí, jinak hodnota HRESULT představující selhání. Pokud dojde k spravované výjimce, vrátí 0x80020009 (DISP_E_EXCEPTION).  
  
### <a name="remarks"></a>Poznámky  
 Volání CleanOnlineAppCache zapne [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] služby, pokud ještě není spuštěná.  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest rozhraní  
 Načte informace o nasazení z manifestu a aktivace adresy URL.  
  
### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|Typ|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|Ukazatel `ActivationURL`.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|Ukazatel `PathToDeploymentManifest`.|LPCWSTR|  
|`pwzApplicationIdentity`|Ukazatel na vyrovnávací paměť pro příjem ukončené hodnotou NULL řetězec, který určuje vrátil úplné identity aplikace.|LPWSTR|  
|`pdwIdentityBufferLength`|Ukazatel na DWORD, který je délka `pwzApplicationIdentity` vyrovnávací paměti v WCHARs. To zahrnuje místa pro ukončovací znak hodnoty NULL.|LPDWORD|  
|`pwzProcessorArchitecture`|Ukazatel na vyrovnávací paměť pro příjem ukončené hodnotou NULL řetězec, který určuje architekturu procesoru nasazení aplikace z manifestu.|LPWSTR|  
|`pdwArchitectureBufferLength`|Ukazatel na DWORD, který je délka `pwzProcessorArchitecture` vyrovnávací paměti v WCHARs.|LPDWORD|  
|`pwzApplicationManifestCodebase`|Ukazatel na vyrovnávací paměť pro příjem ukončené hodnotou NULL řetězec, který určuje základu kódu manifestu aplikace, z manifestu.|LPWSTR|  
|`pdwCodebaseBufferLength`|Ukazatel na DWORD, který je délka `pwzApplicationManifestCodebase` vyrovnávací paměti v WCHARs.|LPDWORD|  
|`pwzDeploymentProvider`|Ukazatel na vyrovnávací paměť pro příjem řetězce ukončené hodnotou NULL určující poskytovatele nasazení z manifestu, pokud je k dispozici. Jinak se vrátí prázdný řetězec.|LPWSTR|  
|`pdwProviderBufferLength`|Ukazatel na DWORD, který je délka `pwzProviderBufferLength`.|LPDWORD|  
  
### <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; Vrátí, jinak hodnota HRESULT představující selhání. Vrátí HRESULTFROMWIN32(ERROR_INSUFFICIENT_BUFFER), pokud vyrovnávací paměť je příliš malá.  
  
### <a name="remarks"></a>Poznámky  
 Ukazatele nesmí mít hodnotu null. `pcwzActivationUrl`a `pcwzPathToDeploymentManifest` nesmí být prázdný.  
  
 Je zodpovědností volajícího vyčistěte adrese URL pro aktivaci. Přidání řídicí znaky například, pokud jsou potřeba nebo odebrání řetězec dotazu.  
  
 Je odpovědností volajícího omezit vstupní délku. Maximální délka adresy URL je například 2KB.  
  
## <a name="launchapplication"></a>LaunchApplication  
 Spustí nebo instaluje aplikace pomocí adresy URL nasazení.  
  
### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|Typ|  
|---------------|-----------------|----------|  
|`deploymentUrl`|Ukazatel na řetězec ukončené hodnotou NULL, který obsahuje adresu URL manifest nasazení.|LPCWSTR|  
|`data`|Vyhrazeno pro budoucí použití. Musí mít hodnotu NULL.|LPVOID|  
|`flags`|Vyhrazeno pro budoucí použití. Musí být 0.|DWORD|  
  
### <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; Vrátí, jinak hodnota HRESULT představující selhání. Pokud dojde k spravované výjimce, vrátí 0x80020009 (DISP_E_EXCEPTION).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>