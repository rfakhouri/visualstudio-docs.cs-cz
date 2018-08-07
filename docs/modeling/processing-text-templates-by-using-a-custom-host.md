---
title: Zpracování textových šablon pomocí vlastního hostitele
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e4546c75f424f5091a22e9acd6cceb72f5d8038c
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2018
ms.locfileid: "39567087"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>Zpracování textových šablon pomocí vlastního hostitele

*Transformace textové šablony* proces trvá *textové šablony* soubor jako vstup a vytvoří textový soubor jako výstup. Můžete volat z stroj pro transformaci textu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, nebo ze samostatné aplikace spuštěné v počítači, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalována. Nicméně je nutné zadat *hostitele šablonování textu*. Tato třída připojuje šablonu k prostředí, vyhledává prostředky, jako jsou sestavení a vkládané soubory, a zpracovává výstup a chybové zprávy.

> [!TIP]
> Pokud vytváříte balíček nebo rozšíření, které poběží v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], zvažte možnost použít službu šablonování textu místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).

> [!NOTE]
> Transformace textových šablon nedoporučujeme používat v serverových aplikacích. Transformace textových šablon nedoporučujeme používat jinak než v jednom vlákně. Stroj pro šablonování textu totiž používá k překladu, kompilaci a spouštění šablon jedinou doménu AppDomain. Přeložený kód není bezpečný pro přístup z více vláken. Tento stroj je určen k sériovému, zpracování souborů se nacházejí v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] v době návrhu projektu.
>
> Pro běhové aplikace zvažte použití předzpracovaných textových šablon: viz [generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

Pokud vaše aplikace používá sadu šablon, které jsou v době kompilace fixní, je jednodušší použít předzpracované textové šablony. Tento přístup můžete také použít, pokud vaše aplikace poběží v počítači, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není nainstalována. Další informace najdete v tématu [generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="execute-a-text-template-in-your-application"></a>Spuštění textové šablony v aplikaci

Ke spuštění textové šablony, můžete volat metody ProcessTemplate třídy <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>:

```csharp
using Microsoft.VisualStudio.TextTemplating;
...
Engine engine = new Engine();
string output = engine.ProcessTemplate(templateString, host);
```

 Vaše aplikace musí najít a poskytnout šablonu a zpracovat výstup.

 V `host` parametr, je nutné zadat třídu, která implementuje <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Tuto třídu zpětně volá stroj.

 Hostitel musí být schopen protokolovat chyby, překládat odkazy na sestavení a vkládané soubory, poskytovat doménu aplikace, ve které se šablona spouští, a volat odpovídající procesor pro jednotlivé direktivy.

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> je definován v **Microsoft.VisualStudio.TextTemplating.\*. 0 knihovna dll**, a <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> je definována v **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0 knihovna dll**.

## <a name="in-this-section"></a>V tomto oddílu
 [Návod: Vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md) ukazuje, jak vytvořit vlastního hostitele textových šablon, která je k dispozici mimo textové šablony funkce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="reference"></a>Odkaz
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>

## <a name="related-sections"></a>Související oddíly

- [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md) popisuje, jak transformace textu fungují, a které části si můžete přizpůsobit.
- [Vytváření vlastních procesorů direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md) obsahuje základní informace o textu procesorů pro direktivy šablon.