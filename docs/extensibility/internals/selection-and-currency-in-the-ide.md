---
title: Výběr a měny v prostředí IDE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- currency, Visual Studio IDE
- IDE, selection
- selection, Visual Studio IDE
- IDE, currency
ms.assetid: 2f6f18d1-acd8-454d-a856-9a4d81155052
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf8c58cb08f82b10970424600843b0fedcf477fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="selection-and-currency-in-the-ide"></a>Výběr a měny v prostředí IDE
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) udržuje informace o uživatelů aktuálně vybrané objekty pomocí výběr *kontextu*. S kontextem výběr VSPackages lze použít při měna sledování dvěma způsoby:  
  
-   Pomocí šíření měna informace o VSPackages k prostředí IDE.  
  
-   Sledováním aktuálně aktivní výběr uživatelů v rámci rozhraní IDE.  
  
## <a name="selection-context"></a>Výběr kontextu  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE globálně uchovává informace o IDE měny v jeho vlastní globální výběr kontextu objektu. Následující tabulka uvádí prvky, které tvoří kontext výběr.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Aktuální hierarchie|Obvykle aktuálním projektu. hierarchie aktuální hodnota NULL znamená, že je aktuální řešení jako celek.|  
|Aktuální ItemID|Vybrané položky v rámci aktuální hierarchii; Pokud existuje více výběrů, v okně projektu, může být více aktuální položky.|  
|Aktuální `SelectionContainer`|Obsahuje jeden nebo více objektů, pro které by měl v okně Vlastnosti zobrazí vlastnosti.|  
  
 Kromě toho prostředí udržuje dva globálních seznamů:  
  
-   Seznam identifikátorů příkaz active uživatelského rozhraní  
  
-   Seznam typů element momentálně aktivní.  
  
### <a name="window-types-and-selection"></a>Typy oken a výběr  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE organizuje windows na dvě obecné typy:  
  
-   Typ hierarchie windows  
  
-   Okna s rámečkem, jako je například nástroje a okna dokumentu  
  
 Prostředí IDE sleduje měna odlišně pro každou z těchto typů okno.  
  
 Okno nejběžnější typu projektu je Průzkumníku řešení, který řídí rozhraní IDE. Okno typu projektu sleduje globální hierarchie a ItemID globální výběr kontextu a okna spoléhá na výběr uživatele k určení aktuální hierarchii. Pro typ projektu windows prostředí poskytuje globální služby <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>, přes které VSPackages můžete sledovat aktuální hodnoty otevřete elementy. Vlastnost procházení v prostředí vycházejí z této globální služby.  
  
 Okna s rámečkem na druhé straně, použijte DocObject v okně s rámečkem tak, aby nabízel SelectionContext hodnoty (hierarchie nebo ItemID nebo SelectionContainer trojici komponent). . Okna s rámečkem používat službu <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> pro tento účel. DocObject můžete posouvat pouze hodnoty pro výběr kontejner, a místní hodnoty pro hierarchii a ItemID beze změny, jako je typický pro dokumenty podřízeného MDI.  
  
### <a name="events-and-currency"></a>Události a měny  
 Může dojít dva typy událostí, které mají vliv prostředí představu o měna:  
  
-   Události, které se rozšíří na globální úrovni a změna kontextu výběr rámce okna. Tento druh událostí příklady okno s podřízeného MDI se otevřít okno globální nástroj otevíráte nebo okno nástroje typu projektu otevíráte.  
  
-   Události, které změnu prvků trasovat v kontextu výběr rámce okna. Mezi příklady patří změna výběru v rámci DocObject nebo změna výběru v okně typu projektu.  
  
## <a name="see-also"></a>Viz také  
 [Výběr objektů kontextu](../../extensibility/internals/selection-context-objects.md)   
 [Zpětná vazba pro uživatele](../../extensibility/internals/feedback-to-the-user.md)