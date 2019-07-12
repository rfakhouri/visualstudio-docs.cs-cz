---
title: Formátování kódu
description: Tento článek popisuje různé možnosti, které lze použít k úpravě chování textového editoru v sadě Visual Studio pro Mac
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 042f7c74057de9a00ae59d5e08a77100c5f30e3c
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67824382"
---
# <a name="editor-behavior"></a>Chování editoru

Chování editoru můžete nastavit tak, aby kód má být formátováno při zápisu. Tyto akce jsou nastavené v rámci **sady Visual Studio > Předvolby > textový Editor > chování**, a některé z nejčastěji používaných funkcí jsou popsané níže:

![Možnosti chování editoru](media/source-editor-image9.png)

* Odpovídající uzavírací složené závorky mohou být automaticky přidán do kódu při vytváření nové třídy, metody nebo vlastnosti. Pokud je vybraná tato možnost, zadáním `{` automaticky přidá `}`.
* Formátování kódu na běhu se aktivuje znak strojů, jako je středníkem nebo složených závorek, které bude emulovat předvolby formátování, které jsou nastavené.
* Můžete také při uložení, která umožňuje zápis kódu podle potřeby a ponechá integrovaného vývojového prostředí za formátování kódu jako sada podle preferencí existující formát souboru.
* Odsazení může být nastaveno na hodnotu None, automaticky, nebo inteligentní. Tyto postupujte takto:
  * NONE – Nastaví blikající kurzor na začátek dalšího řádku
  * Auto – nastaví blikající kurzor na stejný sloupec na dalším řádku
  * Inteligentní – změní odsazení na následující řádek na základě kódu
* Dělení slov chování se liší mezi operační systémy a pro účely navigace, potřebuje vědět, kde slova začátku ani na konci textového editoru. Formátování můžete nastavit pro systém Unix nebo Windows.

Můžete také nastavit pravidla formátování pro XML, šablon stylů CSS, HTML a JSON.

## <a name="see-also"></a>Viz také:

- [Předvolby stylu kódu (Visual Studio na Windows)](/visualstudio/ide/code-styles-and-quick-actions)
