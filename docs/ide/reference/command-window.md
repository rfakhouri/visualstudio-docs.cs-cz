---
title: "Příkaz okno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.CommandWindow
helpviewer_keywords:
- IDE, Command window
- Mark mode in Command window
- Command window
- Command mode in Command window
- IDE Command window
ms.assetid: 48711628-1909-4713-a73e-d7b714c77f8a
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b3b1de69c905757c8d28922cd09eadd5abf7d05e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-window"></a>Příkazové okno
**Příkaz** okno se používá k provedení příkazy nebo přímo v aliasy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Můžete spustit příkazy nabídek a příkazů, které se nezobrazí na žádné nabídky. K zobrazení **příkaz** okně zvolte **ostatní okna** z **zobrazení** nabídce a vyberte **příkazové okno**.  
  
## <a name="displaying-the-values-of-variables"></a>Zobrazení hodnot proměnných  
 Chcete-li zkontrolovat hodnotu proměnné `varA`, použijte [příkaz Tisk](../../ide/reference/print-command.md):  
  
```  
>Debug.Print varA  
```  
  
 Otazník (?) je alias `Debug.Print`, takže můžete zapsat také tento příkaz:  
  
```  
>? varA  
```  
  
 Obě verze tento příkaz vrátí hodnotu proměnné `varA`.  
  
## <a name="entering-commands"></a>Zadávání příkazů  
 Větší než symbol (`>`) se zobrazí na levém okraji příkazové okno příkazovém řádku pro nové řádky. Pomocí klávesy šipka nahoru a dolů šipka možné procházet dřív vydaných příkazů.  
  
|Úloha|Řešení|Příklad|  
|----------|--------------|-------------|  
|Vyhodnocení výrazu.|Adresa výraz otazníkem (`?`).|`? myvar`|  
|Umožňuje přepnout do příkazové podokno.|Zadejte `immed` do okna bez znak větší než (>)|`immed`|  
|Přejít zpět do okna příkaz z příkazové podokno.|Zadejte `cmd` do okna.|`>cmd`|  
  
 Následující zkratky umožňují přejděte v příkazovém režimu.  
  
|Akce|Umístění kurzoru|Keybinding|  
|------------|---------------------|----------------|  
|Procházet seznam dříve zadaných příkazů.|Vstupní řádku|ŠIPKA & DOLŮ ŠIPKA NAHORU|  
|Přejděte do okna.|Obsah příkazového okna|CTRL + ŠIPKA NAHORU|  
|Posuňte se dolů okna.|Obsah příkazového okna|Šipka dolů nebo CTRL + ŠIPKA DOLŮ|  
  
> [!TIP]
>  Vstupní řádek můžete zkopírovat nebo jeho část předchozí příkaz posouvání k němu, zvýraznění všechny nebo jeho část a stisknutím klávesy ENTER.  
  
## <a name="mark-mode"></a>Režim označení  
 Když kliknete na kterýkoli předchozí řádek v **příkaz** okně můžete posunutí automaticky do režimu značky. To umožňuje vybrat, upravovat a zkopírujte text z předchozích příkazů, jako by v každém textovém editoru a vložit do aktuálního řádku.  
  
## <a name="the-equals--sign"></a>Symbolem rovná se (=)  
 Okno používané k zadání `EvaluateStatement` příkaz určuje, zda znak rovná se (=) interpretována jako relační operátor nebo operátor přiřazení.  
  
 V **příkaz** okně znak rovná se (=) interpretována jako operátor porovnání. Operátory přiřazení v nelze použít **příkaz** okno. Ano, například pokud hodnoty proměnných `varA` a `varB` jsou různé a potom příkaz `>Debug.EvaluateStatement(varA=varB)` vrátí hodnotu `False`.  
  
 V **Immediate** okně naopak znak rovná se (=) interpretována jako operátor přiřazení. Tak například příkaz `>Debug.EvaluateStatement(varA=varB)` přiřadí do proměnné `varA` hodnotu proměnné `varB`.  
  
## <a name="parameters-switches-and-values"></a>Parametry, přepínače a hodnoty  
 Některé [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkazy vyžaduje příkazy a volitelné argumenty, přepínače a hodnoty. Při plánování práce s tyto příkazy platí určitá pravidla. Následuje příklad bohaté příkazu o vysvětlení, technologiím.  
  
```  
Edit.ReplaceInFiles /case /pattern:regex var[1-3]+ oldpar   
```  
  
 V tomto příkladu  
  
-   `Edit.ReplaceInFiles`je příkaz  
  
-   `/case`a `/pattern:regex` přepínače (kterými symbolem [/])  
  
-   `regex`je hodnota `/pattern` přepínač; `/case` přepínač nemá žádnou hodnotu  
  
-   `var[1-3]+`a `oldpar` jsou parametry  
  
    > [!NOTE]
    >  Příkaz, parametr, přepínače nebo hodnotu, která obsahuje mezery, musí mít dvojitých uvozovek nahoře na obou stranách.  
  
Pozice přepínače a parametry, můžete zaměnit volně na příkazovém řádku s výjimkou produktů [prostředí](../../ide/reference/shell-command.md) příkaz, který vyžaduje jeho přepínače a parametry v určitém pořadí.  
  
Téměř každý přepínač nepodporuje příkaz má dvě formy: krátkých úseků (jeden znak) a dlouhých úseků. Do skupiny lze spojovat více přepínačů krátké formě. Například `/p /g /m` může být případně vyjádřený jako `/pgm`.  
  
Pokud krátké formě přepínače jsou zkombinované do skupiny a -li zadána hodnota, platí tuto hodnotu pro každý přepínač. Například `/pgm:123` rovná `/p:123 /g:123 /m:123`. Pokud některý z přepínačů ve skupině nepřijímá hodnotu, dojde k chybě.  
  
## <a name="escape-characters"></a>Řídicí znaky  
 Šipka nahoru (^) znak v příkazovém řádku znamená, že znak okamžitě následující ho interpretována oznámena, nikoli jako řídicí znak. To slouží k vložení rovné uvozovky ("), mezery, úvodní lomítka, carets nebo jiných literály hodnotu parametru nebo přepínač, s výjimkou názvy přepínače. Například  
  
```  
>Edit.Find ^^t /regex  
```  

 Šipka nahoru funguje stejně, jestli je uvnitř nebo mimo uvozovky. Pokud šipka nahoru poslední znak v řádku, je ignorován. Z příkladu ukazuje, jak hledat vzor "^ t".  
  
## <a name="use-quotes-for-path-names-with-spaces"></a>Nabídky použijte pro názvy cest prostory  
 Pokud například chcete otevřít soubor, který má cestu obsahující mezery, je nutné umístit dvojité uvozovky kolem cestu nebo cestu segment, který obsahuje mezery: **C:\\"Program Files"** nebo **"C:\Program Files"**.  
  
## <a name="see-also"></a>Viz také  
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)