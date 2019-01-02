---
title: Použití Node.js REPL
description: Visual Studio poskytuje podporu pro práci s modulem runtime Node.js
ms.date: 12/04/2018
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: bdb5202f383a0e9145a03dae71e11894555f5e33
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53926486"
---
# <a name="work-with-the-nodejs-interactive-window"></a>Práce s interaktivní okno Node.js

Nástroje Node.js Tools for Visual Studio zahrnují interaktivní okno pro nainstalovaný modul runtime Node.js. Toto okno umožňuje zadat kód jazyka JavaScript a hned vidět výsledky, také spouštět příkazy npm pro interakci s aktuálním projektem. Interaktivní okno se také označuje jako operace REPL (**R**ečíst /**E**valuate /**P**isknout **L**oop).

## <a name="open-the-interactive-window"></a>Otevřít interaktivní okno

Interaktivní okno můžete otevřít tak, že kliknete pravým tlačítkem na uzel projektu Node.js v Průzkumníku řešení a vyberete **otevřete interaktivní okno Node.js**.

![Interaktivní okno Node.js v kontextové nabídce projektu](../javascript/media/interactivewindow-open-from-project.png)

Výchozí klíče místní otevřete interaktivní okno Node.js se **[CTRL] + K, N**. Nebo na panelu nástrojů můžete otevřít okno výběrem **zobrazení** > **Windows** > **interaktivní okno Node.js**.

## <a name="use-the-repl"></a>Použití REPL

Po otevření, můžete zadávat příkazy.

![Interaktivní okno Node.js](../javascript/media/interactivewindow.png)

Interaktivní okno má několik předdefinovaných příkazů, které začínají předponou tečka abychom je odlišili od žádné funkce jazyka JavaScript, který je deklarovat. Podporovány jsou následující příkazy:

**.CLS, .clear** vymaže obsah okna editor uživatele zůstanou nedotčena kontext historie a spuštění.

**.help** zobrazí nápovědu na zadaný příkaz nebo na všechny dostupné příkazy a klávesové zkratky, pokud není zadaný žádný.

**.Info** zobrazuje informace o aktuální použité Node.js spustitelný soubor.

**.npm** spouští příkaz npm. Pokud řešení obsahuje více než jeden projekt, zadejte cílový projekt pomocí `.npm [projectname] <npm arguments>`.

**.reset** do původního stavu, uchovat historii obnoví prostředí pro spuštění.

**.Save** uloží aktuální relaci REPL do souboru.