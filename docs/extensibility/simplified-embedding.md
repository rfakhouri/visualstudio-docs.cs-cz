---
title: Zjednodušená vkládání | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - simple view embedding
ms.assetid: f1292478-a57d-48ec-8c9e-88a23f04ffe5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c77c7f19ff677ddbe8339c88ef3ea46953e23b7d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66332078"
---
# <a name="simplified-embedding"></a>Zjednodušená vkládání
Zjednodušená vkládání je povolen v editoru při jeho objekt zobrazení dokumentu je prvek (to znamená, že provede podřízený) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní je implementováno s cílem zpracovat příkazy jeho okna. Zjednodušená vkládání editory nemůže hostovat aktivní ovládací prvek. Na následujícím obrázku jsou zobrazeny objekty sloužící k vytvoření editoru s zjednodušená vkládání.

 ![Zjednodušená vkládání Editor grafiky](../extensibility/media/vssimplifiedembeddingeditor.gif "vsSimplifiedEmbeddingEditor") Editor s zjednodušená vkládání

> [!NOTE]
> Objektů na tomto obrázku, pouze `CYourEditorFactory` objekt je potřeba vytvořit standardní souborové editoru. Pokud vytváříte vlastní editor, není nutné implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>, protože editor budou mít svůj vlastní mechanismus privátní trvalosti. Pro jiné vlastní editory ale musíte tak učinit.

 Všechna rozhraní implementované vytvoření editoru s zjednodušená vkládání jsou obsaženy v `CYourEditorDocument` objektu. Však pro podporu více zobrazení dokumentů data rozdělte rozhraní do samostatných dat a zobrazení objektů jak je uvedeno v následující tabulce.

|Rozhraní|Umístění rozhraní|Použití|
|---------------|---------------------------|---------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Zobrazit|Poskytuje připojení do nadřazeného okna.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Zobrazit|Zpracovává příkazy.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|Zobrazit|Povolí aktualizace stavového řádku.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|Zobrazit|Umožňuje **nástrojů** položky.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|Data|Odešle oznámení při změně souboru.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Data|Povolí funkci uložit jako pro určitý typ souboru.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>|Data|Povolí trvalost pro dokument.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|Data|Povolí potlačení událostí změny souborů, jako je aktivace znovu načíst.|