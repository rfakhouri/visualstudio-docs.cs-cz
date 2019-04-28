---
title: Psaní a ladění XAML pomocí horké reload XAML
description: Znovu načíst XAML horké, nebo XAML upravit a pokračovat, umožní vám provádět změny kódu XAML při spuštění aplikace
ms.custom: ''
ms.date: 02/28/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a002c3876eecf0f31a8d104fa235b1208af90699
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929136"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>Programujte a laďte spuštěním kódu XAML s horké znovu načíst XAML v sadě Visual Studio

Visual Studio XAML horké znovu načíst pomůže sestavit aplikaci WPF nebo UWP uživatelského rozhraní tím, že umožňuje provést změny kódu XAML, když vaše aplikace běží. Tato funkce umožňuje přírůstkové sestavování a testování kódu XAML s výhodou poskytovatelů kontext dat spuštěné aplikaci, stav ověření a další složitost reálného světa, která je obtížné simulovat v době návrhu.

Znovu načíst horké XAML je zvláště užitečná v těchto scénářích:

* Oprava problémů se uživatelské rozhraní najít v kódu XAML po spuštění aplikace v režimu ladění.

* Sestavování nové komponenty uživatelského rozhraní pro aplikace, která je ve vývoji s využitím kontext modulu runtime vaší aplikace.

|Typy podporované aplikace|Operační systém a nástroje|
|-|-|-|
|Windows Presentation Foundation (WPF) |Rozhraní .NET framework 4.6 +</br>Windows 7 a vyšší |
|Aplikace pro Universal Windows (UPW)|Windows 10 a novější, s [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> Visual Studio XAML horké se momentálně podporuje jen při spouštění vaší aplikace v sadě Visual Studio s připojeným ladícím nástrojem (**F5** nebo **spustit ladění**). Toto prostředí nemůžete povolit pomocí *připojit k procesu*.

## <a name="known-limitations"></a>Známá omezení

Následující seznam uvádí známé, že omezení XAML za běhu načíst znovu. Obejít omezení, na které narazíte, stačí zastavení ladicího programu a pak dokončete operaci.

|Omezení|WPF|UWP|Poznámky|
|-|-|-|-|
|Vzájemné propojení události pro ovládací prvky, když aplikace běží|Nepodporováno|Není podporováno|Zobrazit chybová zpráva: *Zkontrolujte události se nezdařilo*|
|Vytváření objektů prostředků ve slovníku prostředků, jako například sítě na stránce/okna vaší aplikace nebo *App.xaml*|Nepodporováno|Podporováno|Příklad: přidání ```SolidColorBrush``` do slovníku prostředků pro použití jako ```StaticResource```.</br>Poznámka: Statické prostředky, převaděče stylu a další prvky zapsané do slovníku prostředků lze použít nebo používané při používání horké reload XAML. Vytvoření prostředku se nepodporuje.</br> Změna slovník prostředků ```Source``` vlastnost.| 
|Přidání nových ovládacích prvků, třídy, windows nebo jiné soubory do projektu, když aplikace běží|Nepodporováno|Nepodporováno|Žádný|
|Spravovat balíčky NuGet (přidání/odebrání/aktualizuje balíčky)|Nepodporováno|Nepodporováno|Žádné|
|Změna datové vazby, který používá rozšíření značek {x: Bind}|Není k dispozici|Podporováno v aplikaci Visual Studio 2019 a novějších verzích|Nepodporované ve Visual Studio 2018 a předchozí verze|

## <a name="error-messages"></a>Chybové zprávy

Můžete narazit na následující chyby při použití horké reload XAML.

|Chybová zpráva|Popis|
|-|-|-|
|Zkontrolujte události se nezdařilo|Chyba určuje, že se pokoušíte propojí událost do jednoho z své ovládací prvky, které se nepodporuje, když je aplikace spuštěná.|
|XAML upravit a pokračovat nenašel žádné elementy k aktualizaci.|Dojde k chybě při úpravách, XAML, který mezi horkou znovu načíst nelze aktualizovat ve vaší aplikaci.</br> Tuto chybu lze opravit někdy s použitím vaší běžící aplikaci přejděte do zobrazení, ve kterém se používá XAML.</br> V některých případech tato chyba znamená, že konkrétní změnu nejde použít až po restartování relace ladění. |
|Tato změna se během relace ladění nepodporuje.|Chyba určuje, že změna, kterou se pokoušíte nepodporuje horké reload XAML. Zastavit relaci ladění, proveďte požadovanou změnu a potom restartujte relaci ladění.|