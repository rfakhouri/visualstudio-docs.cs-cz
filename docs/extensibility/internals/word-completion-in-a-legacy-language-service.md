---
title: Ve službě jazyk starší verze aplikace Word dokončení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], IntelliSense Complete Word
- IntelliSense, Complete Word
- Complete Word
ms.assetid: 0ace5ac3-f9e1-4e6d-add4-42967b1f96a6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72ddf4e7c755fdecf562f4c190abfb145e6f9819
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141510"
---
# <a name="word-completion-in-a-legacy-language-service"></a>Dokončení slova ve službě jazyk starší verze
Dokončení slova vyplní chybějící znaky na částečně typu aplikace word. Pokud existuje jenom jeden možné dokončení, slovo byla dokončena, pokud je zadaný znak dokončení. Částečné aplikace word odpovídá více než jednu možnost, zobrazí se seznam možná dokončení. Znak dokončení může být libovolný znak, který se nepoužívá pro identifikátory.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace naleznete v tématu [rozšíření pro Editor a služby, jazyk](../../extensibility/extending-the-editor-and-language-services.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="implementation-steps"></a>Postup implementace  
  
1.  Když uživatel vybere **dokončení Word** z **IntelliSense** nabídce <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> příkaz posílá služba jazyka.  
  
2.  <xref:Microsoft.VisualStudio.Package.ViewFilter> Třída zachytí příkaz i jeho volání <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> metoda pomocí důvodu analýzy <xref:Microsoft.VisualStudio.Package.ParseReason>.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source> Třídy volání a pak <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda získat seznam možných word dokončování a potom zobrazí seznam slova v popisu tlačítka, pomocí <xref:Microsoft.VisualStudio.Package.CompletionSet> – třída.  
  
     Pokud existuje jenom jeden odpovídající aplikace word <xref:Microsoft.VisualStudio.Package.Source> třída dokončení slovo.  
  
 Alternativně Pokud skeneru vrátí hodnotu aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> Pokud je zadán první znak identifikátoru, <xref:Microsoft.VisualStudio.Package.Source> třída to zjistí a volá <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> metoda pomocí důvodu analýzy <xref:Microsoft.VisualStudio.Package.ParseReason>. V takovém případě musíte analyzátor zjistit přítomnost znak Výběr člena a poskytnout seznam členů.  
  
## <a name="enabling-support-for-the-complete-word"></a>Povolení podpory pro dokončení aplikace Word  
 Povolení podpory pro sadu dokončení aplikace word `CodeSense` s názvem parametr předaný <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> atribut uživatele přidružené k balíčku jazyk. Toto nastaví <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> vlastnost na <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy.  
  
 Analyzátor jazyka musí vrátit seznam deklarace v reakci na hodnotu důvod analýzy <xref:Microsoft.VisualStudio.Package.ParseReason>, word dokončení pracovat.  
  
## <a name="implementing-complete-word-in-the-parsesource-method"></a>Implementace dokončení aplikace Word v metodě ParseSource  
 Pro dokončení slova <xref:Microsoft.VisualStudio.Package.Source> třídy volání <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> metodu <xref:Microsoft.VisualStudio.Package.AuthoringScope> třída získat seznam možných word odpovídá. V seznamu musí implementovat třídu, která je odvozená od <xref:Microsoft.VisualStudio.Package.Declarations> třídy. Najdete v článku <xref:Microsoft.VisualStudio.Package.Declarations> třída podrobnosti o metody, je nutné implementovat.  
  
 Pokud seznam obsahuje pouze jednoho slova, pak se <xref:Microsoft.VisualStudio.Package.Source> třída automaticky vloží dané slovo místo částečné aplikace word. Pokud seznam obsahuje více než jeden word <xref:Microsoft.VisualStudio.Package.Source> třída představuje seznam nástroj tip, ze kterého může uživatel vybrat příslušnou volbu.  
  
 Také podívat na příklad <xref:Microsoft.VisualStudio.Package.Declarations> implementaci třídy v [dokončení člen ve službě jazyk starší](../../extensibility/internals/member-completion-in-a-legacy-language-service.md).