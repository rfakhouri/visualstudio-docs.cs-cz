---
title: Data dokumentu a dokument zobrazit ve vlastních editorech | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document data and document view
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7574fad343e2966ab9a8782d472a0491bd29767b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348092"
---
# <a name="document-data-and-document-view-in-custom-editors"></a>Data dokumentu a zobrazení dokumentu ve vlastních editorech
Vlastní editor se skládá ze dvou částí: datový objekt dokumentu a objekt zobrazení dokumentu. Jak naznačují názvy, představuje datový objekt dokumentu textových dat, který se má zobrazit. Podobně objekt zobrazení dokumentů (nebo "Zobrazit") představuje jedno nebo více oken, ve kterém chcete zobrazit datový objekt dokumentu.

## <a name="document-data-object"></a>Datový objekt dokumentu
 Datový objekt dokumentu je reprezentace dat textu ve vyrovnávací paměti textu. Je objekt modelu COM, který ukládá textu v dokumentu a další informace. Datový objekt dokumentu také zpracovává trvalost dokumentu a umožňuje více zobrazení jeho data. Další informace naleznete v tématu

 <xref:EnvDTE80.Window2.DocumentData%2A> a [dokumentu Windows](../extensibility/internals/document-windows.md).

 Vlastních editorů a návrhářů můžete se rozhodnout použít <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objektu nebo své vlastní vlastní vyrovnávací paměti. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> Následující zjednodušený model vkládání pro standardní editor, podporuje více zobrazení a poskytuje rozhraní, které se používají ke správě více zobrazení.

## <a name="document-view-object"></a>Objekt zobrazení dokumentu
 Okno, které se zobrazí kód a další texty se označuje jako dokument zobrazení nebo zobrazení. Při vytváření editoru můžete buď jedno zobrazení, ve kterém se zobrazí text v jednom okně. Nebo můžete použít několik zobrazení, ve kterém se zobrazí text ve více než jedno okno. Výběr závisí na vaší aplikace. Například pokud potřebujete úpravy vedle sebe, vybrali byste více zobrazení. Každé zobrazení souvisí s položkou v integrovaném vývojovém prostředí (IDE) spuštěná tabulka dokumentů (r...). Zobrazení windows patří do projektu nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu.

 Pokud editor podporuje několik zobrazení datového objektu dokumentu, pak vaše data dokumentu a dokument zobrazit objekty musí být odděleny. V opačném případě že mohou být seskupeny. Další informace najdete v tématu [podporovat více zobrazení dokumentů](../extensibility/supporting-multiple-document-views.md).

 Rozhraní IDE upozorní zobrazení o událostech (například při zavření řešení obsahujícího dokumentu) to provede spárováním odpovídajících identifikátor položky (ItemID) pro každý záznam v tabulce spuštěných dokumentů. Další informace najdete v části [spuštěná tabulka dokumentů](../extensibility/internals/running-document-table.md).

 Existují dvě možnosti pro vytvoření zobrazení pro vlastní editor. Jeden je modelu aktivace na místě, kde se hostuje zobrazení v okně pomocí ovládacího prvku ActiveX nebo datový objekt dokumentu. Druhým je zjednodušený model vkládání, kde je hostitelem zobrazení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> je implementováno s cílem zpracovat příkazy okna. Informace o modelu aktivace na místě, naleznete v tématu [aktivace na místě](../extensibility/in-place-activation.md). Informace o modelu zjednodušená vkládání najdete v tématu [zjednodušená vkládání](../extensibility/simplified-embedding.md).

## <a name="see-also"></a>Viz také:
- [Podpora více zobrazení dokumentů](../extensibility/supporting-multiple-document-views.md)
- [Zjednodušená vkládání](../extensibility/simplified-embedding.md)
- [Postupy: Připojení zobrazení k datům dokumentu](../extensibility/how-to-attach-views-to-document-data.md)
- [Správa vlastník zámku dokumentu](../extensibility/document-lock-holder-management.md)
- [Zobrazení jedné a více karet](../extensibility/single-and-multi-tab-views.md)
- [Uložení standardního dokumentu](../extensibility/internals/saving-a-standard-document.md)
- [Trvalost a spuštění tabulky dokumentů](../extensibility/internals/persistence-and-the-running-document-table.md)
- [Určení, které editor otevře soubor v projektu](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)
- [Objekty pro vytváření editoru](../extensibility/editor-factories.md)