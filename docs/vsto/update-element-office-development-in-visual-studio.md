---
title: '&lt;Aktualizovat&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 661aa9c0c1a590e78d20e52b6321294d59e70c63
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988985"
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;Aktualizovat&gt; – element (vývoj pro Office v sadě Visual Studio)
  `update` Prvek určuje interval, ve kterém bude zjišťovat řešení pro aktualizaci.

## <a name="syntax"></a>Syntaxe

```xml
<update
  enabled>
  <expiration
    maximumAge
    unit
  />
</update>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `update` Element je povinný a je v `vstav3` oboru názvů.

 `update` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`enabled`|Povinný parametr. Nastavte enabled na jednu z následujících hodnot:<br /><br /> -   **Hodnota TRUE** ke kontrole aktualizací.<br />-   **false** zabránit, vyhledávají se aktualizace.|

 `update` Element má následující podřízené prvky.

### <a name="expiration"></a>vypršení platnosti
 `expiration` Element je povinný a je v `vstav3` oboru názvů. Tento prvek určuje interval, kdy až řešení příště pro aktualizaci.

 `expiration` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`maximumAge`| Povinný parametr. Nastavte toto na celé číslo.|
|`unit`|Povinný parametr. Nastavte `unit` na jednu z následujících hodnot:<br /><br /> -   **hodiny**<br />-   **dny**<br />-   **týdnů**|

## <a name="example-of-always-checking-for-updates"></a>Příklad vždy vyhledávají se aktualizace

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje `update` element, který je nastavena na vždy vyhledejte aktualizace v řešeních pro systém Office.

### <a name="code"></a>Kód

```xml
<vstav3:update enabled="true" />
```

## <a name="example-of-setting-a-default-update-interval"></a>Příklad nastavení výchozí interval aktualizace

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje `update` elementu v manifestu aplikace pro řešení Office. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstav3:update enabled="true">
    <vstav3:expiration maximumAge="7" unit="days" />
</vstav3:update>
```

## <a name="see-also"></a>Viz také:

- [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)
- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
