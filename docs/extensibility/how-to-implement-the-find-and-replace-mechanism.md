---
title: 'Postupy: implementace najít a nahradit mechanismus | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 45d0b1307d86b32f1def3c4474e1ca25959915c0
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056443"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Postupy: implementace najít a nahradit mechanismus

Visual Studio poskytuje dva způsoby implementace vyhledání a nahrazení. Jedním ze způsobů je předat bitovou kopii text do prostředí a nechat ji zpracovat vyhledávání, zvýraznění a nahraďte text. To umožňuje uživatelům zadat více rozpětí textu. Vaše VSPackage Alternativně můžete řídit tuto funkci, sám sebe. V obou případech musíte upozornit prostředí o aktuální cíl a cíle pro všechny otevřené dokumenty.

## <a name="to-implement-findreplace"></a>K implementaci vyhledání a nahrazení

1. Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> rozhraní na některý z objektů vrácené vlastnosti rámce <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocView> nebo <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocData>. Pokud vytváříte vlastní editor, měli byste implementovat toto rozhraní v rámci třídy vlastní editor.

2. Použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> metoda zadejte možnosti, které podporuje vaše editoru a označuje, zda implementuje hledání textu bitové kopie.

   Pokud vaše editor podporuje hledání textu bitové kopie, implementujte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.

   Jinak, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.

3. Pokud implementujete <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> metod, můžete zjednodušit vyhledávání úkoly voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> rozhraní.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>