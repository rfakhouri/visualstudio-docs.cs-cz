---
title: 'Postupy: Implementace najít a nahradit mechanismus | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 478d3e155486aa146d28c6c9c9b9246fd5d69569
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351952"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Postupy: Implementace najít a nahradit mechanismus

Visual Studio nabízí dva způsoby implementace najít a nahradit. Jedním ze způsobů je předat bitovou kopii text do prostředí a ten zpracování vyhledávání, zvýrazňování a nahrazení textu. To umožňuje uživatelům zadat více rozpětí textu. Alternativně vašeho balíčku VSPackage můžete řídit tento samotné funkce. V obou případech musíte upozornit prostředí o aktuální cíl a cíle pro všechny otevřené dokumenty.

## <a name="to-implement-findreplace"></a>K implementaci najít a nahradit

1. Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> rozhraní na jednom z objektů vrácených podle vlastnosti rámce <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocView> nebo <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocData>. Pokud vytváříte vlastní editor, měli byste implementovat toto rozhraní jako součást třídy vlastní editor.

2. Použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> metoda postup určení možností, které podporuje vaše editoru a označuje, zda implementuje hledání text obrázku.

   Pokud váš editor podporuje text hledání obrázků, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.

   V opačném případě implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.

3. Pokud se rozhodnete implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> metody, můžete zjednodušit hledání úloh pomocí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> rozhraní.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>