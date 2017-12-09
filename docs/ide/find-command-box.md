---
title: "Pole najít příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.findcommandbox
helpviewer_keywords: Find/Command box
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fa54e65ed581d547d7e4a0c6c5d1c1e0908c0ca
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="findcommand-box"></a>pole Najít/příkaz

Můžete hledat text a spustit příkazy sady Visual Studio z **najít/příkaz** pole. **Najít/příkaz** pole je stále k dispozici jako ovládacím prvku panel nástrojů, ale nebude ve výchozím nastavení. Můžete zobrazit **najít/příkaz** pole výběrem **přidat nebo odebrat tlačítka** na **standardní** panelu nástrojů a pak vyberete **najít**.

Ke spuštění [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkaz, adresa se znaménkem větší než (>).

**Najít/příkaz** pole uchovává poslední 20 položek zadaných a zobrazí je v rozevíracím seznamu. Můžete přejít pomocí seznamu tak, že zvolíte klávesy se šipkami.

![Najít &#47; Příkaz pole](../ide/media/findcommandbox.png "FindCommandBox")

## <a name="searching-for-text"></a>Hledání textu

Ve výchozím nastavení, když zadáte text v **najít/příkaz** pole a zvolte **Enter** klíče, Visual Studio vyhledá aktuální okna dokumentu nebo nástroj, pomocí možnosti, které jsou určené v **Najít v souborech** dialogové okno. Další informace najdete v tématu [hledání a nahrazování textu](../ide/finding-and-replacing-text.md).

## <a name="entering-commands"></a>Zadávání příkazů

Použít **najít/příkaz** políčko k vydání jedním [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkaz nebo alias místo Hledat text, adresa příkaz s symbol větší než (>). Příklad:

```
>File.NewFile c:\temp\MyFile /t:"General\Text File"
```

Alternativně můžete také použít příkazové okno k zadání a spuštěním jednoho nebo více příkazů. Některé příkazy nebo aliasy můžete zadat a provedený sami; ostatní vyžaduje argumenty v jejich syntaxi. Seznam příkazů, které mají argumenty najdete v tématu [příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md).

## <a name="escape-characters"></a>Řídicí znaky

Šipka nahoru (^) znak v příkazu znamená, že znak okamžitě následující ho interpretována oznámena, nikoli jako řídicí znak. To slouží k vložení rovné uvozovky ("), mezery, úvodní lomítka, carets nebo jiných literály hodnotu parametru nebo přepínač, s výjimkou názvy přepínače. Příklad:

```
>Edit.Find ^^t /regex
```

Šipka nahoru funguje stejně, jestli je uvnitř nebo mimo uvozovky. Pokud šipka nahoru poslední znak v řádku, je ignorován.

## <a name="see-also"></a>Viz také

[Příkazové okno](../ide/reference/command-window.md)  
[Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)