---
title: Příkaz DslTextTransform
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db916372691ce5e336e142aeb72288193e1ed807
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947050"
---
# <a name="the-dsltexttransform-command"></a>Příkaz DslTextTransform
DslTextTransform.cmd je skript, který volá TextTransform.exe a spustí pomocí běžné možnosti. DslTextTransformation.cmd můžete použít k automatizaci noční sestavení vaší [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projekty. Další informace najdete v tématu [generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).

 DslTextTransform.cmd se nachází v následujícím adresáři:

 **\<Cesta instalace sady Visual Studio SDK > \VisualStudioIntegration\Tools\Bin**

 Jako vstup pro DslTextTransform.cmd můžete určit následující argumenty:

-   Výstupní adresář projektu modelu domény.

-   Výstupní adresář projektu definice návrháře.

-   Umístění textového souboru šablony.

 DslTextTransform.cmd zpracuje zadaný textový soubor šablony pomocí procesory direktiv výchozí a sestavení. Pokud vytvoříte vlastní procesory direktiv, můžete vytvořit vlastní dávkový soubor, který volá TextTransform.exe. V tento dávkový soubor můžete zadat vaše sestavení a přidružené vlastní procesory direktiv.