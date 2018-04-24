---
title: Chování editoru
description: ''
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 5de50299ec1d79f28687e5f49d8169ecd3413279
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="editor-behavior"></a>Chování editoru

Editor chování může být nastaven na kód, který má být formátována zapsané povolit. Tyto akce jsou nastavené v rámci **Visual Studio > Předvolby... > textový Editor > chování**, a některé z nejčastěji používaných funkce jsou popsány níže:

![Možnosti editoru chování](media/source-editor-image9.png)

*  Odpovídající složené závorky uzavírací může automaticky přidat do kódu při vytváření nové třídy, metody nebo vlastnosti. Pokud je vybraná tato možnost, zadejte `{` automaticky přidá `}`.
* Formátování kódu na průběžně se aktivuje při stisknutí znak, jako je například oddělte středníkem nebo složené závorky, které bude emulovat předvolby formátování, které jsou nastavené.
* Můžete také formátu souboru při uložení, což umožňuje psaní kódu podle potřeby a zůstane zodpovědná za formátování kódu jako sada podle preferencí stávající prostředí IDE.
* Odsazení může být nastaveno na hodnotu None, automaticky, nebo inteligentní. Tyto postupujte takto:
 * Žádný - nastaví pomocí kurzoru na začátek na další řádek
 * Auto - nastaví pomocí kurzoru na stejný sloupec na další řádek
 * Inteligentní - odsazení na následující řádek na základě kódu
* Dělení slov chování se liší mezi operační systémy a pro účely navigace, textový editor musí vědět, kde slova začínat ani končit. Formátování, které lze nastavit pro systém Unix nebo Windows.

Můžete také nastavit pravidla formátování kódu XML, CSS, HTML a JSON.