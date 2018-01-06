---
title: "Další informace o chybách návrháře tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.CPlusPlusViewInDiagramNoTypeFound
- vs.classdesigner.CPlusPlusNoTypeFound
- vs.classdesigner.CannotShowBaseType
- vs.classdesigner.MatchOrphanTypesAtLoad
- vs.classdesigner.CannotShowType
- vs.classdesigner.AssociationTypeNotFoundError
- vs.classdesigner.ViewInDiagramNoTypesFound
- vs.classdesigner.CannotImplementInterface
- vs.classdesigner.CannotShowImplementedInterface
- vs.classdesigner.ViewInDiagramUnparsableTypeFound
- vs.classdesigner.AssociationTypeNotFound
- vs.classdesigner.CPlusPlusTypeCannotBeAdded
helpviewer_keywords:
- errors, class diagrams
- errors, Class Designer
- error messages, Class Designer
- Class Designer [Visual Studio], errors
- error messages, class diagrams
- class diagrams, errors
ms.assetid: 79d70e70-704c-4255-ab68-c10d6949470e
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53b61b1fa49ffcbc047d47dd26586b45ae883c5f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="additional-information-about-class-designer-errors"></a>Další informace o chybách návrháře tříd
Návrhář tříd nesleduje umístění zdrojových souborů, takže úprava strukturu projektu nebo přesunutí zdrojové soubory v projektu může způsobit návrhář tříd ke ztrátě informací o typu (zejména typ zdroje typedef, základní třídy nebo přidružení typů). Může dojít chybě, jako **třída Návrhář nemůže zobrazit tento typ**. Pokud tak učiníte, přetáhněte upraveném nebo přemístěné zdrojový kód na diagramu tříd znovu a znovu ji zobrazit.  
  
Pomoc s další chyby a upozornění můžete najít v následujících zdrojích informací:  
  
[Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)  
Obsahuje informace o zobrazení C++ v diagramu tříd pro řešení potíží.  
  
[Fórum návrháře Visual Studio – třída](http://go.microsoft.com/fwlink/?LinkId=160754)  
Poskytuje fórum pro otázky o návrháři tříd.  
  
## <a name="see-also"></a>Viz také
[Navrhování a zobrazování tříd a typů](designing-and-viewing-classes-and-types.md)