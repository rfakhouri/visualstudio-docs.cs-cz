---
title: Klávesnice Excelu Office, nastavení klávesnice, dialogové okno Možnosti
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ExcelOptions.KeyboardMappingScheme
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Excel_Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Excel.Keyboard
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
ms.openlocfilehash: 090e943df2b61352c2342218c3c71c8f0e60eaad
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2019
ms.locfileid: "66836040"
---
# <a name="microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Microsoft Office Excel klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti
  Microsoft Office Excelu nebo v sadě Visual Studio i zpracování klávesových zkratek. Stejnou klávesovou zkratku srozumitelný pro různé příkazy v aplikaci Excel a v sadě Visual Studio. Při otevření v úrovni dokumentu projektu v sadě Visual Studio Excel obdrží jenom jednu aplikaci v čase klíče příkazy místní. Ve výchozím nastavení, Visual Studio obdrží všechny klíče příkazy místní, ale může být Excel přijímat, když je dokument fokus tak, že vyberete **chéma dynamické klávesnice**.

 Pokud používáte klávesovou zkratku, která není přiřazena k příkazu v aplikaci, která je aktuálně zpracovává klávesové zkratky, klávesová zkratka je předána jiné aplikace.

 Možnost, kterou jste vybrali zůstávají v platnosti pro projekty aplikace Excel dokud ho změnit. Výběr neovlivňuje projektů Microsoft Office Word; musí provádět změny pro aplikaci Word pomocí možnosti Microsoft Office Word klávesnice.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Schéma klávesnice Visual Studio** sady Visual Studio obdrží všechny klíče příkazy místní i v případě, že aplikace Excel má fokus. Například, pokud stisknutím funkční klávesy **F5** při Excel má fokus, Visual Studio spustí ladění vašeho řešení.

 **Chéma dynamické klávesnice** sady Visual Studio obdrží klíče příkazy místní pouze v případě, že má fokus. Když aplikace Excel má fokus, aplikace Excel obdrží všechny klíče příkazy místní. Například, pokud stisknutím funkční klávesy **F5** při Excel má fokus, otevře se aplikace Excel **přejít na** dialogové okno. Pokud stisknete **F5** při fokusu sady Visual Studio, Visual Studio spustí ladění vašeho řešení.

## <a name="see-also"></a>Viz také:
- [Microsoft Office Word klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)
