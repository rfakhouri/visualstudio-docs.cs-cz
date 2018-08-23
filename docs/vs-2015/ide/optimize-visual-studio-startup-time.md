---
title: Optimalizace spouštění sady Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing startup time [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c2c31a67ac019435c5131a1ab33600d26c76f32d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696141"
---
# <a name="optimize-visual-studio-startup-time"></a>Optimalizace spouštění sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V ideálním případě sady Visual Studio by měl vždy spustit co nejrychleji. Však rozšíření sady Visual Studio a otevřete nástroj windows mohou nepříznivě ovlivnit rychlost spuštění vzhledem k tomu, že se načítají automaticky při spuštění. **Spravovat výkon sady Visual Studio** okno umožňuje zobrazit nejen funkce a rozšíření, které ovlivňují spouštění sady Visual Studio, ale také umožňuje určit jejich chování při načítání, takže budete mít větší kontrolu nad jak rychle Spuštění sady Visual Studio.

## <a name="control-startup-behavior"></a>Řízení chování při spuštění

Aby prodloužení času spuštění sady Visual Studio "15" nevyužívá během spouštění, načítání rozšíření metodiky zatížení na vyžádání. To znamená, že rozšíření neotevírat ihned poté, co Visual Studio spustí, ale místo toho otevřít asynchronně účtujeme podle potřeby po spuštění. Protože okna nástrojů ponechány otevřené v předchozí relaci sady Visual Studio může zhoršit dobu spuštění, Visual Studio otevře okna nástrojů inteligentnější způsobem, aby se zabránilo dopadu na dobu spuštění.

Pokud sada Visual Studio zjistí pomalé spouštění, zobrazí se místní zpráva, upozorní vás do okna rozšíření nebo nástroj, který je příčinou zpomalení. Zprávy také obsahuje odkaz **spravovat výkon sady Visual Studio** dialogové okno, které obsahuje nástroje a rozšíření windows, které mají vliv na výkon při spuštění. Toto dialogové okno umožňuje změnit nastavení okna nástroje a rozšíření pro zvýšení výkonu při spuštění.

![Spravovat výkon sady Visual Studio – automaticky otevírané okno](../ide/media/vside-perfdialog-popup.PNG "spravovat výkon sady Visual Studio – automaticky otevíraného okna")

**Spravovat výkon sady Visual Studio** dialogové okno obsahuje dvě kategorie: **rozšíření** a **nástroj Windows**.

### <a name="control-extensions"></a>Rozšíření pro ovládací prvky
Pokud rozšíření je zpomalení při spuštění sady Visual Studio, rozšíření se zobrazí v **dialogového okna spravovat výkon sady Visual Studio** pole při výběru jednoho z typů rozšíření. Pokud dopad na dobu spuštění (které je uvedené v části **dopad** oddíl) je nepřijatelně vysoké, můžete nastavit výběrem vždy zakázat rozšíření při spuštění **zakázat** tlačítko. Rozšíření pro budoucí relace můžete znovu povolit pomocí Správce rozšíření nebo dialogovém okně Spravovat výkon sady Visual Studio.

![Spravovat výkon sady Visual Studio – rozšíření](../ide/media/vside-perfdialog-extensions.PNG "spravovat výkon sady Visual Studio – rozšíření")

Kromě spuštění rozšíření můžete také zakázat rozšíření, který se načítá při načítání řešení, nebo když uživatel zadá. Zvolte pouze scénář zobrazíte seznam přidružených rozšíření.

### <a name="control-tool-windows"></a>Řízení oken nástrojů
Pokud panel nástrojů je zpomalení při spuštění sady Visual Studio, můžete také ponechat jeho výchozí chování (díky tomu získáte žádné výhody v rychlost při spouštění) nebo jeho chování můžete přepsat volbou jedné z dvou chování:

- **Nezobrazovat okno při spuštění:** Pokud zvolíte tuto možnost, v okně zadaného nástroje vždy se zavřou při otevření sady Visual Studio, i když ponechány otevřené v předchozí relaci. Panel nástrojů můžete otevřít z nabídky.
- **Automaticky skrýt okno při spuštění:** ponecháte-li panel nástrojů byl otevřen v předchozí relaci, pokud vyberete tuto možnost bude sbalit panel nástrojů skupinu při spuštění inicializace panel nástrojů, aby. To je dobrou volbou, pokud používáte panelu nástrojů často, protože okno nástroje je stále k dispozici, ale má vliv na už nebude mít negativní čas spuštění sady Visual Studio.

![Spravovat výkon sady Visual Studio – okna nástrojů](../ide/media/vside-perfdialog-toolwindows.PNG "spravovat výkon sady Visual Studio – oken nástrojů")

Pokud později změníte své rozhodnutí, můžete některé z těchto možností v vrátit **spravovat výkon sady Visual Studio** dialogové okno. Chcete-li otevřít **spravovat výkon sady Visual Studio** dialogové okno, v panelu nabídky zvolte **pomáhají**, **spravovat výkon sady Visual Studio**.


