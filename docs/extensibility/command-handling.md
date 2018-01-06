---
title: "Zpracování příkazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3ecbff62570067b25aae9ad525138687eb281c9f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-handling"></a>Zpracování příkazů
Jako editor můžete definovat nové příkazy. Příkazy se obvykle zobrazují v nabídce, na panelu nástrojů nebo v kontextové nabídce.  
  
 Další informace o definování příkazy a nabídky najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Služba jazyka můžete řídit, jaké kontextové nabídky se zobrazují v editoru tím, že zachytává <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> výčtu. Alternativně můžete řídit v místní nabídce na základě za značky. Další informace najdete v části [důležité příkazy pro filtry služby jazyk](../extensibility/internals/important-commands-for-language-service-filters.md).  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>Přidání příkazů do editoru kontextové nabídky  
 Pokud chcete přidat příkaz do kontextové nabídky, nejdřív je nutné definovat sadu příkazů nabídky patřící do určité skupiny. Následující příklad je převzat ze souboru .vsct generované v rámci tohoto průvodce [návod: Přidání funkce do vlastního editoru](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<Identifikátor guid nabídky = "guidCustomEditorCmdSet" id = "IDMX_RTF" priority = "0x0000" type = "Context" >  
  
 \<Nadřazený identifikátor guid = "guidCustomEditorCmdSet" id = "0" / >  
  
 \<Řetězce >  
  
 \<ButtonText > CustomEditor kontextovou nabídku\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</ Řetězce >  
  
 \<A nabídek >  
  
 \<Či nabídek >  
  
 Výše uvedený text přidá příkaz nabídky kontextu textem **CustomEditor kontextovou nabídku**. Identifikátor GUID nabídky je, že sadu příkazů, které je vytvořené pomocí tohoto editoru a typ je "Context".  
  
 Můžete také použít předdefinované příkazy, které nemusejí být definován v souboru .vsct. Například pokud si projdete soubor EditorPane.cs vygenerované šablony balíček Visual Studio, zjistíte, že sadu předdefinovaných příkazy, jako například <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> definované <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, jsou zpracovávány v obslužné rutiny příkazů, jako je například metoda onSelectAll.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)