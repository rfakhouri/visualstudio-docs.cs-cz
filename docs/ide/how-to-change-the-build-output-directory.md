---
title: 'Postupy: Změna výstupního adresáře sestavení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e74dfb3c9a5e5ccd4a1e61e15a12991433032e6e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989507"
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení

Zadejte umístění výstupu na základě podle konfigurace (pro ladění, vydání nebo obojí), vygenerované váš projekt.

> [!NOTE]
> Pokud máte **nastavení** projekt, naleznete v poznámce na konci tohoto článku.

## <a name="change-the-build-output-directory"></a>Změna výstupního adresáře sestavení

1.  V panelu nabídky zvolte **projektu** > **\<název_aplikace > vlastnosti**. Můžete také kliknout pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**.

2.  Pokud máte projekt jazyka Visual Basic, vyberte **kompilaci** kartu. Pokud máte projekt C#, vyberte **sestavení** kartu. Pokud máte projekt jazyka C++ nebo JavaScript projektu, vyberte **Obecné** kartu.

3.  V rozevíracího seznamu v horní části konfigurace zvolte konfiguraci, jejíž výstup souboru umístění, které chcete změnit (debug, release nebo všechny).

     Vyhledejte položku výstupní cestu (**výstupní cesta sestavení** v jazyce Visual Basic **výstupní adresář** v jazyce Visual C++ **výstupní cesta** v JavaScriptu a C#). Zadejte nový výstupní adresář sestavení relativní k adresáři projektu.

> [!NOTE]
> V nastavení projektu **název výstupního souboru** pole se změní pouze umístění *Setup.exe* souboru, ne však umístění souborů projektu. Další informace najdete v tématu **sestavení, vlastnosti konfigurace, dialogové okno Vlastnosti projektu nasazení**.

## <a name="see-also"></a>Viz také:

- [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Stránka Obecné vlastností (projekt)](/cpp/ide/general-property-page-project)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)