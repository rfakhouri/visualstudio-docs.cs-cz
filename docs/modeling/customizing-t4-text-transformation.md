---
title: Přizpůsobení transformace textu T4 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 158e39dfe01dd0016d622918082d6ec4874dc661
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="customizing-t4-text-transformation"></a>Přizpůsobení transformace textu T4
Textové šablony jsou funkce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] které umožňují generovat kód programu nebo jiných textových souborů procesem transformace. Pomocí [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)], přizpůsobením procesoru direktiv text šablony nebo hostitele textových šablon můžete rozšířit výchozí proces transformace šablony.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md)  
 Popisuje, jak funguje transformace textu a vysvětluje roli hostitele šablon a procesory direktiv.  
  
 [Vytváření vlastních procesorů pro direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Procesoru direktiv zabývá direktivy v šabloně, jako například `<#@template#>.` spouští během kompilace šablony a můžete načíst sestavení a dalším prostředkům. Můžete vložit také kód, který načte prostředky za běhu. Definování vlastního procesoru direktiv, můžete snížit složitost vašich šablon.  
  
 [Volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 Pokud píšete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, jako jsou nabídky příkaz nebo událostí obslužná rutina, rozšíření můžete použít službu ukázka Text k transformaci žádné textové šablony. Můžete předat parametru data do šablony s použitím objektu Session a získat hodnoty z v rámci šablony pomocí `<#@parameter#>` – direktiva.  
  
 [Zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 Když kód textové šablony provede, hostitel poskytuje přístup k externí soubory a stav aplikace. Například hostiteli, který spouští transformací textu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] může poskytnout přístup do Průzkumníka řešení. Zobrazí také chyby v okně chybové zprávy. Pokud chcete spustit transformací textu v jiném kontextu, můžete definovat vlastní hostitele, který poskytuje přístup ke službám, které jsou k dispozici v tomto kontextu.  
  
 Pokud píšete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, zvažte použití existující službu transformace textu místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
## <a name="reference"></a>Odkaz  
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)  
  
 Poskytuje syntaxe direktivy textových šablon a řídicí bloky.