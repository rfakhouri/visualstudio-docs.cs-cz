---
title: "Přidat existující položku – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a94546b8e480a661c175f946cc376fa92b30cbf8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 / e:`editorname`  
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