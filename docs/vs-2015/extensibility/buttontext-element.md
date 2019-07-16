---
title: ButtonText – Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ef22471d20df5582fec96c8a685029a1d475a4a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184568"
---
# <a name="buttontext-element"></a>ButtonText – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto pole umožňuje zadat text, který se zobrazí v různých nabídkách. Ve výchozím nastavení `ButtonText` elementu se zobrazí v nabídce řadiče. `ButtonText` Prvek stane výchozí Pokud další textová pole jsou prázdné. `ButtonText` Element nemůže být prázdný, i když nejsou určeny další textová pole.  
  
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
|[Strings – element](../extensibility/strings-element.md)|Seskupí textové prvky, jako například `ButtonText` a `CommandName`.|  
  
## <a name="text-value"></a>Textová hodnota  
 Textová hodnota elementu `ButtonText` element obsahuje text, který se zobrazí u položek nabídky, kláves a jiných prvcích uživatelského rozhraní (UI), které mají viditelného textu.  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
