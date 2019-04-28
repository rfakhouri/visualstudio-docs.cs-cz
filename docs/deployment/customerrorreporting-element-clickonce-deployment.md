---
title: '&lt;customErrorReporting&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <customErrorReporting> element [ClickOnce deployment manifest]
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6d42bd1f7304d9f50b6334d9ac8ddd4f626605d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62900368"
---
# <a name="ltcustomerrorreportinggt-element-clickonce-deployment"></a>&lt;customErrorReporting&gt; – element (nasazení ClickOnce)
Určuje identifikátor URI, chcete-li zobrazit, když dojde k chybě.

## <a name="syntax"></a>Syntaxe

```xml
<customErrorReporting
   uri
/>
```

## <a name="remarks"></a>Poznámky
 Tento element je volitelný. Bez něho [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zobrazí dialogové okno chyby zobrazující zásobník výjimek. Pokud `customErrorReporting` element je k dispozici, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] místo toho zobrazí identifikátor URI indikován `uri` parametru. Cílový identifikátor URI bude obsahovat třídy vnější výjimky, vnitřní výjimka třídy a zpráva o vnitřní výjimce jako parametry.

 Tento element slouží k přidání zpráv o chybách funkce do vaší aplikace. Vzhledem k tomu, že vygenerovaný identifikátor URI obsahuje informace o typu chyby, vaše webová stránka může analyzovat a zobrazit, například obrazovku řešení potíží tyto informace.

## <a name="example"></a>Příklad
 Následující fragment kódu ukazuje `customErrorReporting` element spolu s vygenerovaný identifikátor URI může vrátit.

```xml
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />

Example Generated Error:
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)