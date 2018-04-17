---
title: Další informace o chybách návrháře tříd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8cd6223786db06506c1fa4ac9b6bd3118eb5e3d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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