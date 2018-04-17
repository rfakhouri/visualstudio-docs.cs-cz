---
title: Přidat existující položku – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47e1dab5259f5df2a5fee925e70bcec6c3021059
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="add-existing-item-command"></a>Přidat existující položku – příkaz
Přidá k aktuálnímu řešení existující soubor a otevře ji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.AddExistingItem filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Požadováno. Úplná cesta a název, s příponou, položky, které chcete přidat k aktuálnímu řešení. Pokud cesta k souboru nebo název souboru obsahuje mezery, uzavřete celý cesty do uvozovek.  
  
## <a name="switches"></a>Přepínače  
 / e: `editorname`  
 Volitelné. Název editoru, ve kterém bude soubor otevřít. Pokud je argument zadaný ale zadaný žádný název editoru, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` syntaxí argumentů používá názvy editor, jak se zobrazují v **otevřete se dialogové okno**, uzavřené v uvozovkách. Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Poznámky  
 Automatické dokončování pokusí se najít správnou cestu a název souboru při psaní.  
  
## <a name="example"></a>Příklad  
 Tento příklad souboru Form1.frm, přidá k aktuálnímu řešení.  
  
```  
>File.AddExistingItem "C:\public\solution files\Form1.frm"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)