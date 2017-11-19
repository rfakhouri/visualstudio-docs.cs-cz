---
title: ButtonText Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b17492b0cc8531ac892bf8ead1c309f403d1da48
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="buttontext-element"></a>ButtonText Element
Toto pole umožňuje zadat text, který se zobrazí v různých nabídky. Ve výchozím nastavení `ButtonText` prvek se zobrazuje v nabídce řadiče. `ButtonText` Element také změní výchozí, pokud textová pole jsou prázdné. `ButtonText` Element nemůže být prázdný, i když nejsou určeny v ostatních polích text.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Element řetězce](../extensibility/strings-element.md)|Skupiny elementy textu, například `ButtonText` a `CommandName`.|  
  
## <a name="text-value"></a>Textová hodnota  
 Textovou hodnotu `ButtonText` element poskytuje text, který se zobrazí u položky nabídky, kláves a další prvky uživatelského rozhraní (UI), které mají viditelné text.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)