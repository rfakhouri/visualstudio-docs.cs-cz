---
title: Zpracování příkazů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1517410c58646bad2333db95b6f666937d890303
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62926907"
---
# <a name="command-handling"></a>Zpracování příkazů
Editoru můžete definovat nové příkazy. Příkazy se obvykle zobrazují v nabídce, na panelu nástrojů nebo v místní nabídce.

 Další informace o definování příkazů a nabídek, naleznete v tématu [příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).

 Služba jazyka můžete řídit, jaké kontextové nabídky se zobrazí v editoru, tím, že zachytává <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> výčtu. Alternativně můžete řídit kontextové nabídky na základě jednotlivé značky. Další informace najdete v tématu [důležité příkazy pro filtry služby jazyka](../extensibility/internals/important-commands-for-language-service-filters.md).

## <a name="add-commands-to-the-editor-context-menu"></a>Přidání příkazů do kontextové nabídky editoru
 Přidání příkazu do místní nabídky, je nutné nejprve definovat sadu příkazy nabídek, které patří do konkrétní skupiny. V následujícím příkladu se přebírá ze *.vsct* souboru vygenerovaného jako součást návodu [názorný postup: Přidání funkcí do vlastního editoru](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):

 \<Menu guid="guidCustomEditorCmdSet" id="IDMX_RTF" priority="0x0000" type="Context">

 \<Identifikátor guid nadřazené = "guidCustomEditorCmdSet" id = "0" / >

 \<Řetězce >

 \<ButtonText – > CustomEditor kontextovou nabídku\</ButtonText >

 \<CommandName > CustomEditorContextMenu\</CommandName >

 \</Strings>

 \</ Nabídka >

 \</ Nabídky >

 Výše uvedený text přidá příkazu kontextové nabídky s textem **CustomEditor kontextovou nabídku**. Identifikátor GUID nabídky je součástí sady příkazů, který je vytvořen pomocí tohoto editoru. Typ je "Kontext".

 Můžete také použít předdefinované příkazy, které nemusí být definován v *.vsct* souboru. Například zkoumat *EditorPane.cs* soubor generovaný nástrojem pro Visual Studio balíček šablony. Zjistíte, sadu předdefinovaných příkazů, jako například <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> určené <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, jsou zpracovány v obslužné rutiny příkazů, jako `onSelectAll` metoda.

## <a name="see-also"></a>Viz také:
- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)