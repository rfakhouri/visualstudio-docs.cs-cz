---
title: '&lt;compatibleFrameworks&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: c5abcc6e7c4308cf0d60c78cd4ef0f052403bb1f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671969"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; – Element (nasazení ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ &lt;compatibleFrameworks&gt; – Element (nasazení ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/compatibleframeworks-element-clickonce-deployment).  
  
Určuje verzi rozhraní .NET Framework, ve kterém můžete tuto aplikaci nainstalovat a spustit.  
  
> [!NOTE]
>  [MageUI.exe](http://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14) nepodporuje `compatibleFrameworks` element při ukládání manifestu aplikace, který již byl podepsán pomocí certifikátu [MageUI.exe](http://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14). Místo toho je nutné použít [Mage.exe](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `compatibleFrameworks` Element se vyžaduje pro manifesty nasazení, které se zaměřují [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] runtime poskytovaného službou [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] nebo novější. `compatibleFrameworks` Element obsahuje jeden nebo více `framework` elementy, které určují verze rozhraní .NET Framework, na kterých tato aplikace mohla spustit. [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Modul runtime spustí aplikaci v prvním dostupné `framework` v tomto seznamu.  
  
 V následující tabulce jsou uvedeny atribut, který `compatibleFrameworks` elementu podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`S` `upportUrl`|Volitelné. Určuje adresu URL, kde lze stáhnout upřednostňované kompatibilní verze rozhraní .NET Framework.|  
  
## <a name="framework"></a>rozhraní  
 Požadováno. V následující tabulce jsou uvedeny atributy, které `framework` elementu podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`targetVersion`|Požadováno. Určuje číslo verze cílového rozhraní .NET Framework.|  
|`profile`|Požadováno. Určuje profil cílového rozhraní .NET Framework.|  
|`supportedRuntime`|Požadováno. Určuje číslo verze modulu runtime přidružený k cílové rozhraní .NET Framework.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `compatibleFrameworks` prvek [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifestu nasazení. Toto nasazení můžete spustit na [!INCLUDE[net_client_v40_long](../includes/net-client-v40-long-md.md)]. Můžete také spustit [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] vzhledem k tomu, že je nadstavbou jazyka [!INCLUDE[net_client_v40_long](../includes/net-client-v40-long-md.md)].  
  
```  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)



