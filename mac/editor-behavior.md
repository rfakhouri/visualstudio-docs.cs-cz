---
title: "Editor chování | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 3515dfbf3a7cf8c23178aa9df243638f955593e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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