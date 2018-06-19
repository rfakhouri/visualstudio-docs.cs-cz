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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 721b8241a3278ddbf1be3b5477e8829b7aa4447b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942244"
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení

Umístění výstupu můžete zadat na základě za konfigurace (pro ladění, verzi nebo obě), vygenerovaných projektu.

> [!NOTE]
> Pokud máte **instalace** projektu, přečtěte si poznámku na konci tohoto článku.

## <a name="change-the-build-output-directory"></a>Změna výstupního adresáře sestavení

1.  Na řádku nabídek zvolte **projektu** > **\<Appname > vlastnosti**. Můžete také kliknout pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**.

2.  Pokud máte projektu jazyka Visual Basic, vyberte **zkompilovat** kartě. Pokud máte projekt C#, vyberte **sestavení** kartě. Pokud máte projektu jazyka C++ nebo projekt jazyka JavaScript, vyberte **Obecné** kartě.

3.  V konfiguraci rozevírací seznam v horní části, zvolte konfiguraci, jejíž výstup chcete změnit (ladění, vydání nebo všechny) umístění souboru.

     Vyhledejte položku výstupní cesta (**sestavení výstupní cesta** v jazyce Visual Basic **výstupního adresáře** v jazyce Visual C++, **výstupní cesta** v JavaScript a C#). Zadejte nové výstupního adresáře sestavení relativně k adresáři projektu.

> [!NOTE]
> V nastavení projektu **názvu výstupního souboru** pole změní jenom umístění *Setup.exe* souboru, ne však umístění souborů projektu. Další informace najdete v tématu **sestavení, vlastnosti konfigurace, dialogové okno Vlastnosti projektu nasazení**.

## <a name="see-also"></a>Viz také

- [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Stránka Obecné vlastností (projekt)](/cpp/ide/general-property-page-project)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)