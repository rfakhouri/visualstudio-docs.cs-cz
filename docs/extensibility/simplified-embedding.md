---
title: "Zjednodušená vložení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - simple view embedding
ms.assetid: f1292478-a57d-48ec-8c9e-88a23f04ffe5
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4315a55b74d938576572b0630f5dca553643a24
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="simplified-embedding"></a>Zjednodušená vložení
Zjednodušená vložení je povolena v editoru při jeho objekt zobrazení dokumentu je nadřazena má (který je provedeno podřízenou) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní je implementováno pro zpracování jeho příkazy okna. Zjednodušená vnoření editory nemůže být hostitelem aktivní ovládací prvky. Na následujícím obrázku se zobrazí objekty použít k vytvoření editoru s zjednodušené vložení.  
  
 ![Zjednodušená vložení editoru obrázek](../extensibility/media/vssimplifiedembeddingeditor.gif "vsSimplifiedEmbeddingEditor")  
Editor s zjednodušené vložení  
  
> [!NOTE]
>  Objekty v tomto obrázku pouze `CYourEditorFactory` objektu je potřeba vytvořit standardní na základě souborů editor. Pokud vytváříte vlastní editor, není nutné k implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>, protože vaše editor pravděpodobně bude mít svůj vlastní mechanismus privátní trvalosti. Pro jiný vlastní editory ale je potřeba udělat tak.  
  
 Všechna rozhraní implementované vytvořit editoru s zjednodušené vložení jsou součástí `CYourEditorDocument` objektu. Ale pro podporu více zobrazení dat dokumentu, rozdělte rozhraní do samostatné objekty data a podívat se, které je uvedené v následující tabulce.  
  
|Rozhraní|Umístění rozhraní|Použití|  
|---------------|---------------------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Zobrazit|Poskytuje připojení do nadřazeného okna.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Zobrazit|Zpracovává příkazy.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|Zobrazit|Umožňuje aktualizace stavového řádku.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|Zobrazit|Umožňuje **sada nástrojů** položky.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|Data|Odešle oznámení, když se změní soubor.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Data|Povolí funkci uložit jako pro určitý typ souboru.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>|Data|Povolí zachování dokumentu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|Data|Povolí potlačení události změny souborů, jako je například opětovné načtení aktivován.|