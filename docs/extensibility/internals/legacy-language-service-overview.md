---
title: "Přehled služby starší verze jazyka | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services [managed package framework], about language services
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d586851da7d02f89335a3920364e25b7f4876860
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-overview"></a>Přehled služby starší verze jazyka
Služba jazyka poskytuje podporu editor, který umožňuje implementovat určité [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] funkce. Třídy spravované Framework balíčku (MPF) jazyk služby poskytují plnou podporu pro často používané funkce a částečné podporu pro další funkce.  
  
## <a name="fully-supported-features-in-the-mpf"></a>Plně podporované funkce v MPF  
 Třídy sady MPF jazyk služeb podporují následující funkce:  
  
-   zvýraznění syntaxe  
  
-   Sbalování  
  
-   Při psaní komentářů bloky kódu  
  
-   Související závorky  
  
-   Fragmenty kódu  
  
-   Vlastní vlastnosti dokumentu  
  
-   Informace o parametrech IntelliSense  
  
-   Informace o rychlé IntelliSense  
  
-   Člen doplňování IntelliSense  
  
-   Dokončení slova IntelliSense  
  
## <a name="partially-supported-features-in-the-mpf"></a>Částečně podporovaných funkcích v MPF  
 Sady MPF poskytuje pouze částečný podporu pro následující funkce. To znamená, že musí implementovat metody, které jsou volány MPF.  
  
-   Přeformátování kód. Můžete zadat kód, který implementuje přeformátování.  
  
-   Ověřování zarážky určením platný kód zahrnuje. Můžete zadat kód, který identifikuje kódu rozpětí.  
  
-   Podpora ladicího programu **automobily** okno pro zobrazení proměnné. Můžete zadat kód, který určuje, co se zobrazí v okně.  
  
-   Podpora **navigační panel** rychlé navigace mezi typy a členy. Můžete implementovat a pomocná třída, která naplní seznamy v **navigační panel** pole se seznamem.  
  
## <a name="implementation"></a>Implementace  
 Je třeba provést několik kroky pro implementaci samotnou službu jazyka a jazykové funkce služby, které chcete zajistit podporu pro svůj jazyk. Tyto kroky jsou popsané v následujících tématech:  
  
-   [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [Syntaxe barevné ve službě jazyk starší verze](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [Související závorky ve službě jazyk starší verze](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [Osnova ve službě jazyk starší verze](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [Přidávání poznámek kódu ve službě jazyk starší verze](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [Přeformátování kódu ve službě jazyk starší verze](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [Vlastní vlastnosti dokumentu ve službě jazyk starší verze](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [Podpora pro fragmenty kódu ve službě jazyk starší verze](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [Podpora pro navigační panel ve službě jazyk starší verze](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [Dokončení slova ve službě jazyk starší verze](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [Dokončení člen ve službě jazyk starší verze](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [Informace o parametrech ve službě jazyk starší verze](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [Rychlé informace ve službě jazyk starší verze](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [Podpora pro automobily okna ve službě jazyk starší verze](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [Ověřování zarážky ve službě jazyk starší verze](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>Viz také  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Rozšíření služby starší verze jazyka](../../extensibility/internals/legacy-language-service-extensibility.md)