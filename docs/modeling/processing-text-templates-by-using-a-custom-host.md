---
title: "Zpracování textových šablon pomocí vlastního hostitele | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
ms.assetid: affa3296-854d-47d6-9685-285f6d9ba5dc
caps.latest.revision: "33"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 5f4456899b724d8a7cd2dba6039b28eee29bfafd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="processing-text-templates-by-using-a-custom-host"></a>Zpracování textových šablon pomocí vlastního hostitele
*Transformace textu šablony* zpracovat trvá *textové šablony* souboru jako vstup a vytváří textový soubor jako výstup. Můžete volat transformační modul text z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, nebo z samostatné aplikace běžící na počítači, na kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalovaná. Nicméně je nutné zadat *ukázka hostitele textových*. Tato třída připojuje šablonu k prostředí, vyhledává prostředky, jako jsou sestavení a vkládané soubory, a zpracovává výstup a chybové zprávy.  
  
> [!TIP]
>  Pokud píšete balíček nebo rozšíření, které se spustí v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], zvažte použití služby ukázka textu, místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
> [!NOTE]
>  Transformace textových šablon nedoporučujeme používat v serverových aplikacích. Transformace textových šablon nedoporučujeme používat jinak než v jednom vlákně. Stroj pro šablonování textu totiž používá k překladu, kompilaci a spouštění šablon jedinou doménu AppDomain. Přeložený kód není bezpečný pro přístup z více vláken. Modul je určená ke zpracování souborů sériově, jako jsou ve [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu v době návrhu.  
>   
>  Pro spuštění aplikace, zvažte použití předběžně zpracované textové šablony: najdete v části [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Pokud vaše aplikace používá sadu šablon, které jsou v době kompilace fixní, je jednodušší použít předzpracované textové šablony. Tuto metodu můžete také použijte, pokud vaše aplikace spustí na počítači, na kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není nainstalována. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="executing-a-text-template-in-your-application"></a>Spuštění textové šablony v aplikaci  
 Spuštění textové šablony, zavolejte metodu ProcessTemplate <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>:  
  
```  
using Microsoft.VisualStudio.TextTemplating;  
...  
Engine engine = new Engine();  
string output = engine.ProcessTemplate(templateString, host);  
```  
  
 Vaše aplikace musí najít a poskytnout šablonu a zpracovat výstup.  
  
 V `host` parametru, je nutné zadat třídu, která implementuje <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Tuto třídu zpětně volá stroj.  
  
 Hostitel musí být schopen protokolovat chyby, překládat odkazy na sestavení a vkládané soubory, poskytovat doménu aplikace, ve které se šablona spouští, a volat odpovídající procesor pro jednotlivé direktivy.  
  
 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>je definována v **Microsoft.VisualStudio.TextTemplating.\*. 0 knihovny dll**, a <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> je definována v **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0 knihovny dll**.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Návod: Vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md)  
 Ukazuje, jak vytvořit vlastní text hostitele šablony, která je k dispozici mimo text šablony funkce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>  
  
## <a name="related-sections"></a>Související oddíly  
 [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md)  
 Popisuje, jak transformace textu fungují, a které části si můžete přizpůsobit.  
  
 [Vytváření vlastních procesorů pro direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Poskytuje přehled procesorů direktiv textových šablon.