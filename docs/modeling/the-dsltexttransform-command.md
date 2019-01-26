---
title: Příkaz DslTextTransform
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 97ddf1fb9dd9e59c2d00f3733069a5cdb14553bf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037899"
---
# <a name="the-dsltexttransform-command"></a>Příkaz DslTextTransform
DslTextTransform.cmd je skript, který volá TextTransform.exe a spustí pomocí běžné možnosti. DslTextTransformation.cmd můžete použít k automatizaci noční sestavení z vašeho [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projekty. Další informace najdete v tématu [generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).

 DslTextTransform.cmd se nachází v následujícím adresáři:

 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**

 Jako vstup pro DslTextTransform.cmd lze zadat následující argumenty:

- Výstupní adresář projektu s modelem domény.

- Výstupní adresář projektu definice návrháře.

- Umístění souboru textové šablony.

  DslTextTransform.cmd zpracovává zadaný textový soubor šablony pomocí procesorů pro direktivy výchozí a sestavení. Pokud vytvoříte vlastní procesory direktiv, můžete vytvořit vlastní dávkový soubor, který volá TextTransform.exe. V tomto souboru služby batch můžete zadat sestavení a přidružené vlastní procesory direktiv.