---
title: Rozšíření pro Editor a jazyk služby | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new -
ms.assetid: 8d04f8db-eda7-4b3e-b6eb-c06df104502a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4113a033d4e1a2595f4a980405e1b39d57d60958
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132571"
---
# <a name="extending-the-editor-and-language-services"></a>Rozšíření pro Editor a jazyk služby
Můžete přidat vlastní editor jazykové funkce služby (například IntelliSense) a rozšířit většinu funkcí editoru kódu v sadě Visual Studio.  Úplný seznam co můžete rozšířit, najdete v části [služba jazyka a body rozšíření editoru](../extensibility/language-service-and-editor-extension-points.md).  
  
 Většinu funkcí editor rozšíříte pomocí Managed Extensibility Framework (MEF). Pokud chcete rozšířit funkce editor zvýrazňování syntaxe, můžete například napsat MEF *součást* , který definuje klasifikace, pro které chcete různé barevné zvýrazňování a jejich zpracování. Editor také podporuje několik rozšíření stejné funkce.  
  
 Prezentační vrstva editor je založená Windows Presentation Framework (WPF). WPF poskytuje knihovnu grafiky pro formátování textu, flexibilní a také poskytuje vizualizace, například grafika a animace.  
  
 Visual Studio SDK poskytuje adaptérů, označované jako *překrytí* pro podporu VSPackages napsaných pro starší verze. Nicméně pokud máte existující VSPackage, doporučujeme aktualizovat na novou technologií získat lepší výkon a spolehlivost.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Začínáme s rozšířeními pro služby jazyka a editor](../extensibility/getting-started-with-language-service-and-editor-extensions.md)|Popisuje postup vytvoření rozšíření pro editor.|  
|[Práce v editoru](../extensibility/inside-the-editor.md)|Popisuje obecnou strukturu editoru a uvádí některé z jeho funkcí.|  
|[Managed Extensibility Framework v editor](../extensibility/managed-extensibility-framework-in-the-editor.md)|Vysvětluje, jak používat Managed Extensibility Framework (MEF) pomocí editoru.|  
|[Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)|Uvádí body rozšíření editoru. Rozšíření body představují editor funkce, které je možné rozšířit.|  
|[Návod: Vytvoření grafického doplňku zobrazení, příkazů a nastavení (vodítka sloupců)](../extensibility/walkthrough-creating-a-view-adornment-commands-and-settings-column-guides.md)|Provede a vysvětluje vytváření zobrazení dalších úprav, který se vykreslí řádky gudie sloupec vám pomůže ochránit kódu do určité šířky zobrazení.  Také ukazuje čtení a zápis nastavení a také deklarace a implementace příkazy, které můžete vyvolat z příkazové okno.|  
|[Importy do editoru](../extensibility/editor-imports.md)|Zobrazí seznam služeb, které můžete importovat rozšíření.|  
|[Přizpůsobení starší verze kódu do editoru](../extensibility/adapting-legacy-code-to-the-editor.md)|Popisuje různé způsoby, jak přizpůsobit starším kódu (předem Visual Studio 2010) pro rozšíření editoru.|  
|[Migrace služby starší verze jazyka](../extensibility/internals/migrating-a-legacy-language-service.md)|Vysvětluje, jak k migraci služby VSPackage na základě jazyka.|  
|[Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)|Ukazuje, jak propojit příponu názvu souboru typu obsahu.|  
|[Návod: Vytvoření okrajového piktogramu](../extensibility/walkthrough-creating-a-margin-glyph.md)|Ukazuje, jak přidat ikonu na okraj.|  
|[Návod: Zvýraznění textu](../extensibility/walkthrough-highlighting-text.md)|Ukazuje, jak používat *značky* zvýraznění textu.|  
|[Návod: Sbalení](../extensibility/walkthrough-outlining.md)|Ukazuje, jak přidat osnovy pro specifické druhy složené závorky.|  
|[Návod: Zobrazení párových složených závorek](../extensibility/walkthrough-displaying-matching-braces.md)|Ukazuje, jak zvýraznění odpovídající složené závorky.|  
|[Návod: Zobrazení popisů tlačítek s rychlými informacemi](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)|Ukazuje, jak zobrazit QuickInfo automaticky otevíraná okna, které popisují elementy kódu třeba vlastnosti, metod a události.|  
|[Návod: Zobrazení vyhrazené nápovědy](../extensibility/walkthrough-displaying-signature-help.md)|Ukazuje, jak zobrazit automaticky otevíraná okna, které poskytují informace o počtu a typů parametrů v podpis.|  
|[Návod: Zobrazení dokončování příkazů](../extensibility/walkthrough-displaying-statement-completion.md)|Ukazuje, jak implementovat dokončování.|  
|[Návod: Implementace fragmentů kódu](../extensibility/walkthrough-implementing-code-snippets.md)|Ukazuje, jak implementovat rozšíření fragmentu kódu.|  
|[Návod: Zobrazení návrhů v podobě žárovky](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)|Ukazuje, jak zobrazit žárovek návrhy kódu.|  
|[Návod: Použití příkazů prostředí s rozšířením editoru](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)|Ukazuje, jak přidružit příkazu nabídky v VSPackage komponentu MEF.|  
|[Návod: Použití klávesové zkratky s rozšířením editoru](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)|Ukazuje, jak pro přidružení místní nabídky v VSPackage komponentu MEF.|  
|[MEF (Managed Extensibility Framework)](/dotnet/framework/mef/index)|Poskytuje informace o Managed Extensibility Framework (MEF).|  
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Poskytuje informace o Windows Presentation Foundation (WPF).|  
  
## <a name="reference"></a>Odkaz  
 Editoru Visual Studio obsahuje následující obory názvů.  
  
 <xref:Microsoft.VisualStudio.Language.Intellisense>  
  
 <xref:Microsoft.VisualStudio.Language.StandardClassification>  
  
 <xref:Microsoft.VisualStudio.Editor>  
  
 <xref:Microsoft.VisualStudio.Text>  
  
 <xref:Microsoft.VisualStudio.Text.Adornments>  
  
 <xref:Microsoft.VisualStudio.Text.Classification>  
  
 <xref:Microsoft.VisualStudio.Text.Differencing>  
  
 <xref:Microsoft.VisualStudio.Text.Document>  
  
 <xref:Microsoft.VisualStudio.Text.Editor>  
  
 <xref:Microsoft.VisualStudio.Text.Editor.OptionsExtensionMethods>  
  
 <xref:Microsoft.VisualStudio.Text.Formatting>  
  
 <xref:Microsoft.VisualStudio.Text.IncrementalSearch>  
  
 <xref:Microsoft.VisualStudio.Text.Operations>  
  
 <xref:Microsoft.VisualStudio.Text.Outlining>  
  
 <xref:Microsoft.VisualStudio.Text.Projection>  
  
 <xref:Microsoft.VisualStudio.Text.Tagging>  
  
 <xref:Microsoft.VisualStudio.Utilities>