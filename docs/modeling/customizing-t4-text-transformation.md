---
title: Přizpůsobení transformace textu T4
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 33f7fd14ff62369de66e4934bf9bb2cf6fd83542
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62994767"
---
# <a name="customize-t4-text-transformation"></a>Přizpůsobení transformace textu T4

Textové šablony jsou funkce sady Visual Studio, které umožňují generování programového kódu nebo jiných textových souborů pomocí transformace procesu. Pomocí [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)], přizpůsobením procesor direktiv šablony textu nebo hostitele textových šablon můžete rozšířit výchozí proces transformace šablon.

## <a name="in-this-section"></a>V tomto oddílu

 [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md) popisuje, jak transformace textu fungují a vysvětluje roli hostitele šablon a procesorů direktiv.

 [Vytváření vlastních procesorů direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md) procesoru direktiv se zabývá direktivy v šabloně, jako například `<#@template#>.` spustí během kompilace šablony a můžete načíst sestavení a další prostředky. Můžete také vložit kód, který načte prostředky v době běhu. Definuje vlastní procesor direktiv, lze omezit složitost vaší šablony.

 [Volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md) Pokud píšete rozšíření sady Visual Studio, jako je například obslužnou rutinu příkazu nebo událost nabídky, rozšíření můžete použít službu Šablonování textu k transformaci všechny textové šablony. Můžete předat data parametrů do šablony s použitím objektu relace a získat hodnoty z v rámci šablony s použitím `<#@parameter#>` směrnice.

 [Zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md) při spustí kód textové šablony, hostitel poskytuje přístup k externí soubory a stav aplikace. Například můžete hostitele, na kterém běží transformace textu v sadě Visual Studio poskytují přístup k **Průzkumníka řešení**. Zobrazí také chyby v okně chybové zprávy. Pokud chcete spustit transformace textu v jiném kontextu, můžete definovat vlastního hostitele, který poskytuje přístup ke službám v tomto kontextu k dispozici.

 Pokud píšete rozšíření sady Visual Studio, zvažte použití existující službu transformace textu místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="reference"></a>Odkaz

- [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md) poskytuje syntaxe direktivy textové šablony a řídicí bloky.