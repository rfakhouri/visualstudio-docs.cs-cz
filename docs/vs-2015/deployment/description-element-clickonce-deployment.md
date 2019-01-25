---
title: '&lt;Popis&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cadf4a0b525e5603247748edd63516dc26d8a0b6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54776218"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Popis&gt; – Element (nasazení ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje informace o aplikaci použít k vytvoření prostředí prezentace a **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `description` Element je povinný a je v `urn:schemas-microsoft-com:asm.v1` oboru názvů. Neobsahuje žádné podřízené prvky a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`publisher`|Povinný parametr. Určuje název společnosti použít pro umístění ikony v Windows **Start** nabídky a **přidat nebo odebrat programy** v Ovládacích panelech, když je nasazení nakonfigurováno pro instalaci.|  
|`product`|Povinný parametr. Určuje úplný název produktu. Použít jako název ikona nainstalované v Windows **Start** nabídky.|  
|`suiteName`|Volitelné. Identifikuje podsložku v rámci `publisher` složky v Windows **Start** nabídky.|  
|`supportUrl`|Volitelné. Určuje adresu URL podpory, který je zobrazen v **přidat nebo odebrat programy** v Ovládacích panelech. Je také vytvořen zástupce na tuto adresu URL pro podporu aplikace v Windows **Start** nabídky, pokud je nasazení nakonfigurováno pro instalaci.|  
  
## <a name="remarks"></a>Poznámky  
 Ve všech konfiguracích nasazení je vyžadován popis prvek.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `description` prvek [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifestu nasazení. Tento příklad kódu je součástí většího příkladu určeného pro [Manifest nasazení ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.  
  
```  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)
