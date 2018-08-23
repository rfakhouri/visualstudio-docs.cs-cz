---
title: '&lt;Plány&gt; – Element (zaváděcí nástroj) | Dokumentace Microsoftu'
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
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: c72ee64bcc174bcd11d800bbc8dd0e1b9848b746
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670355"
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Plány&gt; – Element (zaváděcí nástroj)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ &lt;plány&gt; – Element (zaváděcí nástroj)](https://docs.microsoft.com/visualstudio/deployment/schedules-element-bootstrapper).  
  
`Schedules` Obsahuje element `Schedule` prvky, které definují konkrétní časy, ve které příkazy určené `Command` element by měl být spuštěn.  
  
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
 `Schedules` Element je podřízeným prvkem `Product` elementu. Každý `Product` element může obsahovat nanejvýš jeden `Schedules` elementu. `Schedules` Prvek nemá žádné atributy.  
  
## <a name="schedule"></a>Plán  
 `Schedule` Element je podřízeným prvkem `Schedules` elementu. A `Schedules` element musí mít aspoň jeden `Schedule` elementu.  
  
 `Schedule` má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Název položky plánu. To odpovídá `ScheduleName` vlastnost `Command` elementu. Když `Command` odkazuje na pojmenovanou plánu, bude spuštěn pouze v době uvedené díky tomu `Schedule` element. Plány mohou také být přiřazena `FailIf` a `BypassIf` prvky, které omezují tyto testy podmíněného spouštění podle zadaného plánu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
  
 A vzhledem `Schedule` element může mít nastavený právě jeden z následujících podřízených prvků.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` Element dává pokyn k provedení příkazu okamžitě po spuštění zaváděcí aplikace Instalační služby.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` Element dává pokyn k provedení příkazu, než bude nainstalován zadaný balíček Instalační služby.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` Element instruuje instalační program ke spuštění příkazu po zadaný balíček nainstalován.  
  
## <a name="see-also"></a>Viz také  
 [\<Produkt > – Element](../deployment/product-element-bootstrapper.md)   
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)



