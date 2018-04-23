---
title: '&lt;Plány&gt; prvek (zavaděče) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4cbc6b4f5ebd400d90466ccfa353d679a766580
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Plány&gt; – Element (zaváděcího nástroje)
`Schedules` Obsahuje element `Schedule` elementy, které definují konkrétní časy, ve které příkazy definované `Command` element by měl být spuštěn.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Schedules>  
    <Schedule  
        Name  
    >  
        <BuildList />  
        <BeforePackage />  
        <AfterPackage />  
    </Schedule>  
</Schedules>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `Schedules` Element je podřízená `Product` elementu. Každý `Product` element může mít maximálně jeden `Schedules` elementu. `Schedules` Element nemá žádné atributy.  
  
## <a name="schedule"></a>Plán  
 `Schedule` Element je podřízená `Schedules` elementu. A `Schedules` element musí mít alespoň jeden `Schedule` elementu.  
  
 `Schedule` má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Název položky plánu. To odpovídá `ScheduleName` vlastnost `Command` elementu. Když `Command` odkazuje na pojmenované plán, bude spuštěn pouze v době uvedené v tomto `Schedule` element. Plány mohou být také přidruženy `FailIf` a `BypassIf` prvky, které omezují podmíněných testů spouštění podle zadaného plánu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
  
 A zadané `Schedule` element může mít přesně jeden z následujících podřízených prvků.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` Element dá pokyn ke spuštění příkazu ihned po startu zaváděcí aplikace Instalační služby.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` Element dá pokyn ke spuštění příkazu před instalací zadaný balíček Instalační služby.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` Element dá pokyn ke spuštění příkazu po instalaci zadaný balíček Instalační služby.  
  
## <a name="see-also"></a>Viz také  
 [\<Produkt > elementu](../deployment/product-element-bootstrapper.md)   
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)