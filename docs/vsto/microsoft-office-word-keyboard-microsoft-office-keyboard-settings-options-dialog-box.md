---
title: Microsoft Office Word klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Word.Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Word_Keyboard
- VST.WordOptions.KeyboardMappingScheme
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- keyboard shortcuts, Office development in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6506fec976822ea4a4e675c9961395c952a7a35f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604090"
---
# <a name="microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Microsoft Office Word klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti
  Aplikace Microsoft Office Word a sady Visual Studio i zpracování klávesových zkratek. Stejnou klávesovou zkratku srozumitelný pro různé příkazy v aplikaci Word a v sadě Visual Studio. Při otevření v úrovni dokumentu projektu v sadě Visual Studio slovo obdrží jenom jednu aplikaci v čase klíče příkazy místní. Ve výchozím nastavení, Visual Studio obdrží všechny klíče příkazy místní, ale může být slovo přijímat, když je dokument fokus tak, že vyberete **chéma dynamické klávesnice**.

 Pokud používáte klávesovou zkratku, která není přiřazena k příkazu v aplikaci, která je aktuálně zpracovává klávesové zkratky, klávesová zkratka je předána jiné aplikace.

 Možnost, kterou jste vybrali zůstávají v platnosti pro Wordové projekty dokud ho změnit. Výběr neovlivňuje projektů Microsoft Office Excel; musí provádět změny pro aplikaci Excel pomocí možnosti Microsoft Office Excel klávesnice.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Schéma klávesnice Visual Studio** sady Visual Studio obdrží všechny klíče příkazy místní i v případě, že dokument aplikace Word má fokus. Například, pokud stisknutím funkční klávesy **F5** při dokumentu má fokus, Visual Studio spustí ladění vašeho řešení.

 **Chéma dynamické klávesnice** sady Visual Studio obdrží klíče příkazy místní pouze v případě, že má fokus. Jakmile se Wordový dokument má fokus, Word přijímat všechny klíče příkazy místní. Například, pokud stisknutím funkční klávesy **F5** při Wordový dokument má fokus, otevře se aplikace Word **najít a nahradit** dialogové okno s **přejít na** vybraná karta. Pokud stisknete **F5** při fokusu sady Visual Studio, Visual Studio spustí ladění vašeho řešení.

## <a name="see-also"></a>Viz také:
- [Microsoft Office Excel klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)
