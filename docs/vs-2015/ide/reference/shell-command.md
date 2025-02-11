---
title: Shell příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- tools.shell
helpviewer_keywords:
- exe files
- Shell command
- Tools.Shell command
- executables, running from Visual Studio
- .exe files
- Shell, launching exe files
- Visual Studio, executables from
ms.assetid: 737fda23-b852-45c4-a9fe-41cbce6ba70f
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a85b8ef5dd99da6c82c9f63da31bec783a7c9a7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438022"
---
# <a name="shell-command"></a>Prostředí – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Spouští spustitelné programy v rámci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Tools.Shell [/command] [/output] [/dir:folder] path [args]  
```  
  
## <a name="arguments"></a>Arguments  
 `path`  
 Povinný parametr. Cestu a název souboru pro spuštění nebo dokument otevřít. Úplná cesta je vyžadována, pokud zadaný soubor není v jednom z adresářů v proměnné prostředí PATH.  
  
 `args`  
 Volitelné. Všechny argumenty k předání do vyvolaný program.  
  
## <a name="switches"></a>Přepínače  
 [/CommandWindow [nebo] / Command nebo] /c [nebo] / cmd  
 Volitelné. Určuje, že se v zobrazí výstup pro spustitelný soubor **příkaz** okna.  
  
 /dir:`folder` [nebo] / d: `folder`  
 Volitelné. Určuje pracovní adresář bude nastaven při spuštění programu.  
  
 / outputwindow [nebo] / Output [nebo] parametr/out [nebo] /o  
 Volitelné. Určuje, že se v zobrazí výstup pro spustitelný soubor **výstup** okna.  
  
## <a name="remarks"></a>Poznámky  
 Musí být zadán přepínačích /c /o /dir ihned po `Tools.Shell`. Nic zadaných po název spustitelného souboru, jsou předány jako argumenty příkazového řádku.  
  
 Předdefinované alias `Shell` lze použít místo `Tools.Shell`.  
  
> [!CAUTION]
> Pokud `path` argument určuje cestu k adresáři, jakož i název souboru, celý název cesty by měl uzavřete do literálu uvozovky ("" "), protože v následujících tématech:  
  
```  
Tools.Shell """C:\Program Files\SomeFile.exe"""  
```  
  
 Každá sada tří dvojité uvozovky ("" ") je interpretována `Shell` procesoru jako jeden dvojitými uvozovkami. Díky tomu se v předchozím příkladu skutečně předá následující řetězec cesty `Shell` příkaz:  
  
```  
"C:\Program Files\SomeFile.exe"  
```  
  
> [!CAUTION]
> Pokud není uzavřít řetězec cesty v uvozovkách literálu ("" "), Windows použije pouze část řetězce až po první místo. Například pokud výše uvedené cestě řetězec nebyly správně v uvozovkách, by vypadalo Windows pro soubor s názvem "Program", které jsou umístěné v kořenovém adresáři C:\. Pokud spustitelný soubor C:\Program.exe byly ve skutečnosti k dispozici, i jeden nainstaloval nedovolené úmyslné poškozování, Windows by pokus o spuštění tohoto programu místo požadované "c:\Program Files\SomeFile.exe" program.  
  
## <a name="example"></a>Příklad  
 Následující příkaz využívá xcopy.exe zkopírovat soubor `MyText.txt` do `Text` složky. Zobrazí se výstup z xcopy.exe v obou **příkazové okno** a **výstup** okna.  
  
```  
>Tools.Shell /o /c xcopy.exe c:\MyText.txt c:\Text\MyText.txt  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Okno výstup](../../ide/reference/output-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
