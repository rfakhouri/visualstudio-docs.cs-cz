---
title: "Poskytnutí automatizace pro kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa1c2fa5d0da738057e59cdac007c499a834bc0a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="providing-automation-for-code"></a>Poskytnutí automatizace pro kód
Vytvoření modelu automatizace kódu se nevyžaduje. Sada SDK prostředí neposkytuje ukázku jak to udělat. Přehled o kód – modely, najdete v článku <xref:EnvDTE.CodeModel> objektu.  
  
 K implementaci model kódu, je nutné implementovat všechny rozhraní, která jsou určena strukturu interních datových. Objekty musí být odvozen od `IDispatch` třídy.  
  
 Objekty, které můžete rozšířit, <xref:EnvDTE.CodeModel> a <xref:EnvDTE.FileCodeModel>, jsou k dispozici na <xref:EnvDTE.Project> objektu a vypadat třeba takto:  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 Můžete vybrat, zda implementovat jenom na `CodeModel` nebo `FileCodeModel` rozhraní v objektu, kterou vrátíte z vaší `Project` a <xref:EnvDTE.ProjectItem> objekty. Zadejte všechny funkce z tohoto rozhraní, která je vhodná pro váš systém projektu.  
  
 Pokud chcete přidat funkce, jako je například metody nebo vlastnosti, které nejsou k dispozici prostřednictvím standardní `CodeModel` a `FileCodeModel` rozhraní, vytvořte vlastní rozhraní, která dědí z standardní. Ujistěte se, že dokumentů s systému vašeho projektu, koncoví uživatelé věděli, že vyhledejte ho. Vrátí standardní rozhraní, ale můžete volat uživatele `QueryInterface` metoda nebo přetypování na vaše rozhraní, pokud je znám neexistuje.  
  
## <a name="see-also"></a>Viz také  
 [Přehled modelu automatizace](../../extensibility/internals/automation-model-overview.md)