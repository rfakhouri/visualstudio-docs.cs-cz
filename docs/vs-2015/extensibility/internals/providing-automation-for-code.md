---
title: Poskytování automatizace pro kód | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d70958f88bcd48ce3e2a18f2b086367800541a22
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49172872"
---
# <a name="providing-automation-for-code"></a>Poskytování automatizace pro kód
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vytvoření modelu automatizace kódu se nevyžaduje. Sada SDK prostředí neposkytuje ukázku to udělat. Přehled o tom, modely kódu, najdete v článku <xref:EnvDTE.CodeModel> objektu.  
  
 K implementaci modelu kódu, je nutné implementovat všechna rozhraní, které jsou určeny vnitřní datovou strukturu. Objekty musí být odvozen od `IDispatch` třídy.  
  
 Objekty, které můžete rozšířit <xref:EnvDTE.CodeModel> a <xref:EnvDTE.FileCodeModel>, jsou k dispozici na <xref:EnvDTE.Project> objektu a vypadat nějak takto:  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 Můžete se rozhodnout k implementaci jenom `CodeModel` nebo `FileCodeModel` rozhraní v objektu, kterou vrátíte z vaší `Project` a <xref:EnvDTE.ProjectItem> objekty. Zadejte všechny funkce z tohoto rozhraní, která je vhodná pro váš systém projektu.  
  
 Pokud chcete přidat funkce, jako je například metody nebo vlastnosti, které nejsou k dispozici prostřednictvím standardu `CodeModel` a `FileCodeModel` rozhraní, vytvořte vlastní rozhraní, která dědí z normy. Ujistěte se, že dokument s váš systém projektu tak, že koncoví uživatelé vědí, vyhledejte ho. Vrátí standardní rozhraní, ale uživatel může volat `QueryInterface` metody nebo přetypování do vašeho rozhraní, pokud je známo, že existují.  
  
## <a name="see-also"></a>Viz také  
 [Přehled modelu automatizace](../../extensibility/internals/automation-model-overview.md)

