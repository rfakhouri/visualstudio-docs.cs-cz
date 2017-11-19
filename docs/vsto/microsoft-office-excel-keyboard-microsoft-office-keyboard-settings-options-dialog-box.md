---
title: "Aplikace Microsoft Office Excel klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ExcelOptions.KeyboardMappingScheme
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Excel_Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Excel.Keyboard
dev_langs:
- VB
- CSharp
helpviewer_keywords: keyboard shortcuts, Office development in Visual Studio
ms.assetid: 2a8b9e70-66fa-4461-8039-b6d8a2fbb963
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 57e3edf9b8d3f81ebbed6a02f2ff3097321f8074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>Klávesnice aplikace Office Excel sady Microsoft Office, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti
  Aplikace Microsoft Office Excel a Visual Studio i zpracovávat klávesové zkratky. Pro jiné příkazy v aplikaci Excel a v sadě Visual Studio může být mít stejné klávesová zkratka. V případě, že aplikace Excel je otevřený v projektech na úrovni dokumentu v sadě Visual Studio, obdrží pouze jednu aplikaci najednou klíče příkazy místní. Ve výchozím nastavení, Visual Studio přijme všechny příkazy klíče zástupce, ale provedete Excel přijímat dokument má výběrem **schéma dynamické klávesnice**.  
  
 Pokud používáte klávesovou zkratku, která není přiřazen k příkazu v aplikaci, která je aktuálně zpracovává klávesové zkratky, klávesová zkratka je předán jinou aplikaci.  
  
 Možnost, která jste vybrali bude zůstávají platná pro projekty aplikace Excel, dokud ho změnit. Výběr neovlivňuje projektů Microsoft Office Word; je nutné provést změnu pro aplikaci Word pomocí možnosti Microsoft Office Word klávesnice.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Schéma klávesnice Visual Studio**  
 Visual Studio obdrží všechny klíče příkazy místní i v případě, že má právě fokus, aplikace Excel. Například pokud jste stisknutím funkční klávesy F5 při má právě fokus, Excel, Visual Studio spustí ladění řešení.  
  
 **Schéma dynamické klávesnice**  
 Visual Studio přijímá příkazy místní klíče jenom v případě, že je zaměřen. V případě, že aplikace Excel má právě fokus, obdrží Excel všechny příkazy klíče zástupce. Například pokud jste stisknutím funkční klávesy F5 při má právě fokus, Excel, aplikace Excel otevře **přejít na** dialogové okno. Pokud jste stiskněte klávesu F5 má právě fokus, Visual Studio, Visual Studio spustí ladění řešení.  
  
## <a name="see-also"></a>Viz také  
 [Dialogové okno klávesnice, nastavení klávesnice sady Microsoft Office, možnosti aplikace Microsoft Office Word](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)  
  
  