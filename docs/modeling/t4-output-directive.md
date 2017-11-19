---
title: "T4 Výstup – direktiva | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a14993-47ad-4f2e-8032-57db28d5842a
caps.latest.revision: "4"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: bf96406356799a0953ee34eb736266267fe74510
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="t4-output-directive"></a>T4 – direktiva Output
V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] textové šablony `output` – direktiva se používá k definování kódování souboru transformovaných a příponu názvu souboru.  
  
 Například pokud vaše [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekt obsahuje soubor šablony s názvem **MyTemplate.tt** obsahující následující direktivu:  
  
 `<#@output extension=".cs"#>`  
  
 potom [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vygeneruje soubor s názvem **MyTemplate.cs**  
  
 `output` – Direktiva nevyžaduje v běhu (předběžně zpracované) textové šablony. Místo toho, aplikace získá generované řetězec voláním `TextTransform()`. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="using-the-output-directive"></a>Using – direktiva Output  
  
```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 Měla by existovat více než jeden `output` direktivy v každé šabloně text.  
  
## <a name="extension-attribute"></a>atribut rozšíření  
 Určuje příponu názvu souboru výstupního souboru generovaný text.  
  
 Výchozí hodnota je **.cs**  
  
 Příklady:  
 `<#@ output extension=".txt" #>`  
  
 `<#@ output extension=".htm" #>`  
  
 `<#@ output extension=".cs" #>`  
  
 `<#@ output extension=".vb" #>`  
  
 Přípustné hodnoty:  
 Všechny platnou příponu názvu souboru.  
  
## <a name="encoding-attribute"></a>kódování atributu  
 Určuje kódování použité při vygenerování výstupní soubor. Příklad:  
  
 `<#@ output encoding="utf-8"#>`  
  
 Výchozí hodnota je kódování použité k textovému souboru šablony.  
  
 Přípustné hodnoty:  
 `us-ascii`  
  
 `utf-16BE`  
  
 `utf-16`  
  
 `utf-8`  
  
 `utf-7`  
  
 `utf-32`  
  
 `0`(Výchozí nastavení systému)  
  
 Obecně platí, můžete použít název_webového_serveru řetězec nebo číslo CodePage každého kódování vrácený <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>.