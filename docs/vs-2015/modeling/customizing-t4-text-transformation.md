---
title: Přizpůsobení transformace textu T4 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ea2881cfebaf10d7a72e8651214cf3a6f64debae
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54778637"
---
# <a name="customizing-t4-text-transformation"></a>Přizpůsobení transformace textu T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Textové šablony jsou funkce [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , které umožňují generování programového kódu nebo jiných textových souborů pomocí transformace procesu. Pomocí [!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)], přizpůsobením procesor direktiv šablony textu nebo hostitele textových šablon můžete rozšířit výchozí proces transformace šablon.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md)  
 Popisuje, jak transformace textu fungují a vysvětluje roli hostitele šablon a procesorů direktiv.  
  
 [Vytváření vlastních procesorů pro direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Procesoru direktiv se zabývá direktivy v šabloně, jako například `<#@template#>.` spustí během kompilace šablony a můžete načíst sestavení a další prostředky. Můžete také vložit kód, který načte prostředky v době běhu. Definuje vlastní procesor direktiv, lze omezit složitost vaší šablony.  
  
 [Volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 Pokud píšete [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příponu, třeba nabídce příkazu nebo obslužné rutiny události, rozšíření můžete použít službu Šablonování textu k transformaci všechny textové šablony. Můžete předat data parametrů do šablony s použitím objektu relace a získat hodnoty z v rámci šablony s použitím `<#@parameter#>` směrnice.  
  
 [Zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 Když spustí kód textové šablony, hostitel poskytuje přístup k externí soubory a stav aplikace. Například hostitele, na kterém běží transformace textu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] může poskytnout přístup do Průzkumníka řešení. Zobrazí také chyby v okně chybové zprávy. Pokud chcete spustit transformace textu v jiném kontextu, můžete definovat vlastního hostitele, který poskytuje přístup ke službám v tomto kontextu k dispozici.  
  
 Pokud píšete [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření, zvažte možnost použít existující službu transformace textu místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
## <a name="reference"></a>Odkaz  
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)  
  
 Poskytuje syntaxi direktivy textové šablony a řídicí bloky.
