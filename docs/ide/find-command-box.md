---
title: Pole najít příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findcommandbox
helpviewer_keywords:
- Find/Command box
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 215ab2501f3221a9235c75d5a9b28f631692b1de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="findcommand-box"></a>pole Najít/příkaz

Můžete hledat text a spustit příkazy sady Visual Studio z **najít/příkaz** pole. **Najít/příkaz** pole je stále k dispozici jako ovládacím prvku panel nástrojů, ale nebude ve výchozím nastavení. Můžete zobrazit **najít/příkaz** pole výběrem **přidat nebo odebrat tlačítka** na **standardní** panelu nástrojů a pak vyberete **najít**.

Ke spuštění [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkaz, adresa s více než (**>**) přihlášení.

**Najít/příkaz** pole uchovává poslední 20 položek zadaných a zobrazí je v rozevíracím seznamu. Můžete přejít pomocí seznamu tak, že zvolíte **klávesy se šipkami**.

![Najít&#47;příkaz pole](../ide/media/findcommandbox.png "FindCommandBox")

## <a name="searching-for-text"></a>Hledání textu

Ve výchozím nastavení, když zadáte text v **najít/příkaz** pole a zvolte **Enter** klíče, Visual Studio vyhledá aktuální okna dokumentu nebo nástroj, pomocí možnosti, které jsou určené v **Najít v souborech** dialogové okno. Další informace najdete v tématu [vyhledání a nahrazení textu](../ide/finding-and-replacing-text.md).

## <a name="entering-commands"></a>Zadávání příkazů

Použít **najít/příkaz** políčko k vydání jedním [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkaz nebo alias místo Hledat text, adresa příkaz s více než (**>**) symbol. Příklad:

```
>File.NewFile c:\temp\MyFile /t:"General\Text File"
```

Alternativně můžete také použít **příkaz** okno k zadání a spustit jeden nebo více příkazů. Některé příkazy nebo aliasy můžete zadat a provedený sami; ostatní vyžaduje argumenty v jejich syntaxi. Seznam příkazů, které mají argumenty najdete v tématu [příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md).

## <a name="escape-characters"></a>Řídicí znaky

Šipka nahoru (**^**) znak v příkazu znamená, že znak okamžitě následující ho interpretována oznámena, nikoli jako řídicí znak. To slouží k vložení rovné uvozovky (**"**), lomítka úvodní mezery, carets nebo jiné literálové znaky v parametru nebo přepínač hodnoty, s výjimkou názvy přepínače. Příklad:

```
>Edit.Find ^^t /regex
```

Šipka nahoru funguje stejně, jestli je uvnitř nebo mimo uvozovky. Pokud šipka nahoru poslední znak v řádku, je ignorován.

## <a name="see-also"></a>Viz také

[Příkazové okno](../ide/reference/command-window.md)  
[Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)