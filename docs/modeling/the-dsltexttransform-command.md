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
ms.openlocfilehash: 89d83da450014ebf29e2882438d27f9284c9bbbb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939031"
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