---
title: Přehled služby starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], about language services
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8c48c146c38acf905b08ca756e69053dfd6aac28
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040564"
---
# <a name="legacy-language-service-overview"></a>Přehled služby starší verze jazyka
Služba jazyka podporuje editor, který umožňuje implementovat určité [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] funkce. Třídy služeb Managed Package Framework (MPF) jazyka poskytují úplnou podporu pro často používané funkce a částečně se podporuje další funkce.  
  
## <a name="fully-supported-features-in-the-mpf"></a>Plně podporované funkce v MPF  
 Třídy MPF language service podporují následující funkce:  
  
-   Zvýrazňování syntaxe  
  
-   Sbalování  
  
-   Při psaní komentářů bloky kódu  
  
-   Párování závorek  
  
-   Fragmenty kódu  
  
-   Vlastní vlastnosti dokumentu  
  
-   Informace o parametrech technologie IntelliSense  
  
-   Informace o parametru technologie IntelliSense  
  
-   Doplňování technologie IntelliSense člena  
  
-   Doplňování technologie IntelliSense aplikace word  
  
## <a name="partially-supported-features-in-the-mpf"></a>Částečně podporované funkce v MPF  
 MPF poskytuje jenom částečnou podporu pro následující funkce. To znamená, že je nutné implementovat metody, které jsou volány MPF.  
  
-   Přeformátování kódu. Zadáte kód, který implementuje přeformátování.  
  
-   Ověřování zarážek určením platný kód zahrnuje. Zadáte kód, který identifikuje kódu rozpětí.  
  
-   Podpora ladicího programu **automatické hodnoty** okno pro zobrazení proměnné. Zadáte kód, který určuje, co se má zobrazit v okně.  
  
-   Podpora **navigační panel** pro rychlou navigaci mezi typy a členy. Implementace a vracet pomocnou třídu, která naplní seznamy v **navigační panel** polích se seznamem.  
  
## <a name="implementation"></a>Implementace  
 Musíte dokončit několik kroků při implementaci samotnou službu jazyka a tato služba nabízí jazyka, které chcete zajistit podporu pro jazyk. Tyto kroky jsou popsány v následujících tématech:  
  
-   [Implementace služby starší verze jazyka](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [Související závorky ve službě starší verze jazyka](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [Osnova ve službě starší verze jazyka](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [Kód komentářů ve službě starší verze jazyka](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [Přeformátování kódu ve službě starší verze jazyka](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [Vlastní vlastnosti dokumentu ve službě starší verze jazyka](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [Podpora pro fragmenty kódu ve službě starší verze jazyka](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [Podpora navigačního panelu ve službě starší verze jazyka](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [Dokončování slov ve službě starší verze jazyka](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [Dokončování členů ve službě starší verze jazyka](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [Informace o parametrech ve službě starší verze jazyka](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [Rychlé informace ve službě starší verze jazyka](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [Podpora okna Automatické hodnoty ve službě starší verze jazyka](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [Ověřování zarážek ve službě starší verze jazyka](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>Viz také  
 [Implementace služby starší verze jazyka](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Rozšíření služeb starší verze jazyka](../../extensibility/internals/legacy-language-service-extensibility.md)