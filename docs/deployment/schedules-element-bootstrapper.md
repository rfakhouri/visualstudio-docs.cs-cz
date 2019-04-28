---
title: '&lt;Plány&gt; – Element (zaváděcí nástroj) | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2f6e4ae90dbd36dab4f4df7f72d5ecf57ee04b1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62927329"
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Plány&gt; – element (zaváděcí nástroj)
`Schedules` Obsahuje element `Schedule` prvky, které definují konkrétní časy, ve které příkazy určené `Command` element by měl být spuštěn.

## <a name="syntax"></a>Syntaxe

```xml
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
|`Name`|Povinný parametr. Název položky plánu. To odpovídá `ScheduleName` vlastnost `Command` elementu. Když `Command` odkazuje na pojmenovanou plánu, bude spuštěn pouze v době uvedené díky tomu `Schedule` element. Plány mohou také být přiřazena `FailIf` a `BypassIf` prvky, které omezují tyto testy podmíněného spouštění podle zadaného plánu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|

 A vzhledem `Schedule` element může mít nastavený právě jeden z následujících podřízených prvků.

## <a name="buildlist"></a>BuildList
 `BuildList` Element dává pokyn k provedení příkazu okamžitě po spuštění zaváděcí aplikace Instalační služby.

## <a name="beforepackage"></a>BeforePackage
 `BeforePackage` Element dává pokyn k provedení příkazu, než bude nainstalován zadaný balíček Instalační služby.

## <a name="afterpackage"></a>AfterPackage
 `AfterPackage` Element instruuje instalační program ke spuštění příkazu po zadaný balíček nainstalován.

## <a name="see-also"></a>Viz také:
- [\<Produkt > – element](../deployment/product-element-bootstrapper.md)
- [Referenční dokumentace schématu produktů a balíčků](../deployment/product-and-package-schema-reference.md)