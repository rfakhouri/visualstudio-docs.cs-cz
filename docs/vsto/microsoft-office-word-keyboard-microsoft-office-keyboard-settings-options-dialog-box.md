---
title: Aplikace Microsoft Office Word klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d8747485ced6309bf9e63ecf864c67a111ce6c47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Klávesnice aplikace Word sady Microsoft Office, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti
  Aplikace Microsoft Office Word a Visual Studio i zpracovávat klávesové zkratky. Pro jiné příkazy v aplikaci Word a v sadě Visual Studio může být mít stejné klávesová zkratka. V případě, že je slovo otevřete v projektu úrovni dokumentu v sadě Visual Studio, obdrží pouze jednu aplikaci najednou klíče příkazy místní. Ve výchozím nastavení, Visual Studio přijme všechny příkazy klíče zástupce, ale můžete také nastavit přijímat při dokument má právě fokus, výběrem **schéma dynamické klávesnice**.  
  
 Pokud používáte klávesovou zkratku, která není přiřazen k příkazu v aplikaci, která je aktuálně zpracovává klávesové zkratky, klávesová zkratka je předán jinou aplikaci.  
  
 Možnost, která jste vybrali bude zůstávají platná pro projekty aplikace Word, dokud ho změnit. Výběr neovlivňuje projektů Microsoft Office Excel; je nutné provést změnu pro aplikaci Excel pomocí možnosti Microsoft Office Excel klávesnice.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Schéma klávesnice Visual Studio**  
 Visual Studio obdrží všechny klíče příkazy místní i v případě, že má právě fokus, dokument aplikace Word. Například pokud jste stisknutím funkční klávesy F5 při dokument má právě fokus, Visual Studio spustí ladění řešení.  
  
 **Schéma dynamické klávesnice**  
 Visual Studio přijímá příkazy místní klíče jenom v případě, že je zaměřen. V případě, že dokument aplikace Word má právě fokus, Word obdrží všechny příkazy klíče zástupce. Například pokud jste při má právě fokus, dokument aplikace Word stisknutím funkční klávesy F5, Word otevře **najít a nahradit** dialogové okno s **přejít na** vybrána karta. Pokud jste stiskněte klávesu F5 má právě fokus, Visual Studio, Visual Studio spustí ladění řešení.  
  
## <a name="see-also"></a>Viz také  
 [Klávesnice aplikace Office Excel systému Microsoft Office, nastavení klávesnice systému Microsoft Office, dialogové okno Možnosti](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)  
  
  