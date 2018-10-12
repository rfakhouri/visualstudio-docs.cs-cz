---
title: ButtonText – Element | Dokumentace Microsoftu
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
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f5ec72ffd7d0cc96b1ce66098efcfbda4fc30390
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49255330"
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

