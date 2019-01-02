---
title: Zobrazení interakce vrstvy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf907b11a715f9e108c71daeb6bebd35be9f1212
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967093"
---
# <a name="tier-interactions-view"></a>Zobrazení interakcí vrstev

Profilování interakce vrstev poskytuje další informace o časy spuštění funkcí s více vrstvami aplikace, které komunikují s databázemi prostřednictvím [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]. Data se shromažďují pouze pro synchronní volání.

**Požadavky**

- Visual Studio Enterprise

Zobrazení interakcí zobrazí dat interakce vrstev do dvou podoken:

- V hlavním podokně se hierarchického stromu. Na nejvyšší úrovni řádek obsahuje agregovaná data pro připojení databáze [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] stránky nebo proces. Podřízené uzly obsahují agregovaná data pro připojení databáze nadřazeného prvku.

- Po kliknutí na uzel volání databáze v hlavním podokně se zobrazí data pro instanci volání databáze v podokně podrobností.

  Čas se zobrazí jako počet milisekund, nebo počet taktů procesoru. Chcete-li změnit časová jednotka zobrazí, klikněte na tlačítko **nástroje** nabídky, klikněte na tlačítko **možnosti**a pak vyberte jednu z **podle hodnoty času zobrazit** možnosti.

## <a name="master-pane"></a>Hlavní podokno

|Sloupec|Popis|
|------------|-----------------|
|**Název**|-Pro řádek nejvyšší úrovně, název profilovaný proces nebo webové stránky.<br />-Pro řádek připojení databáze, název serveru, který je hostitelem databáze.|
|**Database**|Název databáze (pouze řádky připojení databáze).|
|**Počet**|Celkový počet požadavků, které jsou generovány podle procesu, webové stránky nebo připojení k databázi.|
|**Celkový uplynulý čas**|Celkový čas strávený spouštěním jakékoli jeden požadavek z procesu, webové stránky nebo připojení k databázi.|
|**Maximální uplynulý čas**|Maximální doba trvání provádění jedné žádosti z procesu, webové stránky nebo připojení k databázi.|
|**Minimální uplynulý čas**|Minimální čas, který byl stráven spouštěním jakékoli jeden požadavek z procesu, webové stránky nebo připojení k databázi.|
|**Průměrný uplynulý čas**|Průměrný čas strávený spouštěním žádost z procesu, webové stránky nebo připojení k databázi.|

## <a name="database-connection-details-pane"></a>Podokno podrobností o připojení databáze

|Sloupec|Popis|
|------------|-----------------|
|**Text příkazu**|Dotaz SQL požadavku.|
|**Počet dotazů**|Počet, kolikrát byl dotaz spuštěn.|
|**Celkový uplynulý čas**|Celkový čas strávený spouštěním instance dotazu.|
|**Maximální uplynulý čas**|Maximální čas, který byl stráven spouštěním jakoukoli jednu instanci dotazu.|
|**Minimální uplynulý čas**|Minimální čas, který byl stráven spouštěním jakoukoli jednu instanci dotazu.|
|**Průměrný uplynulý čas**|Průměrný čas strávený spouštěním instanci dotazu.|