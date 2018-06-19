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
ms.openlocfilehash: 7a47580ef347c71ecc2218816b07afc06c3866a3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950056"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>Proces textových šablon pomocí vlastního hostitele

*Transformace textu šablony* zpracovat trvá *textové šablony* souboru jako vstup a vytváří textový soubor jako výstup. Můžete volat transformační modul text z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, nebo z samostatné aplikace běžící na počítači, na kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalovaná. Nicméně je nutné zadat *ukázka hostitele textových*. Tato třída připojuje šablonu k prostředí, vyhledává prostředky, jako jsou sestavení a vkládané soubory, a zpracovává výstup a chybové zprávy.

> [!TIP]
> Pokud píšete balíček nebo rozšíření, které se spustí v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], zvažte použití služby ukázka textu, místo psaní vlastního hostitele. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).

> [!NOTE]
> Transformace textových šablon nedoporučujeme používat v serverových aplikacích. Transformace textových šablon nedoporučujeme používat jinak než v jednom vlákně. Stroj pro šablonování textu totiž používá k překladu, kompilaci a spouštění šablon jedinou doménu AppDomain. Přeložený kód není bezpečný pro přístup z více vláken. Modul je určená ke zpracování souborů sériově, jako jsou ve [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu v době návrhu.
>
> Pro spuštění aplikace, zvažte použití předběžně zpracované textové šablony: najdete v části [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

Pokud vaše aplikace používá sadu šablon, které jsou v době kompilace fixní, je jednodušší použít předzpracované textové šablony. Tuto metodu můžete také použijte, pokud vaše aplikace spustí na počítači, na kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není nainstalována. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="execute-a-text-template-in-your-application"></a>Spuštění textové šablony v aplikaci

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

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> je definována v **Microsoft.VisualStudio.TextTemplating.\*. 0 knihovny dll**, a <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> je definována v **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0 knihovny dll**.

## <a name="in-this-section"></a>V tomto oddílu
 [Návod: Vytvoření vlastního hostitele textových šablon](../modeling/walkthrough-creating-a-custom-text-template-host.md) ukazuje, jak vytvořit vlastní text hostitele šablony, která je k dispozici mimo text šablony funkce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="reference"></a>Odkaz
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>

## <a name="related-sections"></a>Související oddíly

- [Proces transformace textových šablon](../modeling/the-text-template-transformation-process.md) popisuje, jak funguje transformace textu, a které části je můžete přizpůsobit.
- [Vytváření vlastní T4 Text šablony direktiva procesory](../modeling/creating-custom-t4-text-template-directive-processors.md) poskytuje přehled textu procesory direktiv šablony.