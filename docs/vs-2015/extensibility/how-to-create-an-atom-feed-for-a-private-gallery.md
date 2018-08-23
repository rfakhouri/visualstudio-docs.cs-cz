---
title: 'Postupy: vytvoření Atom pro privátní galerii | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c6d46129a77d0d6e0b764f2921dce77014b865f7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685112"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Postupy: vytvoření Atom pro privátní galerii
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření informačního kanálu Atom pro privátní galerii](https://docs.microsoft.com/visualstudio/extensibility/how-to-create-an-atom-feed-for-a-private-gallery).  
  
Můžete vytvořit kanál Atom (RSS) do umístění v intranetu, která obsahuje rozšíření a přidání informačního kanálu do **rozšíření a aktualizace** jako privátní galerie. Další informace najdete v tématu [privátní Galerie](../extensibility/private-galleries.md).  
  
## <a name="creating-an-atom-feed"></a>Vytváření Atom informačního kanálu  
 Vytvořit jako soukromou galerii informačního kanálu Atom, nejdřív shromážděte rozšíření (soubory VSIX) do složky. Můžete je uspořádat do podsložky potřebujete. Budete také potřebovat následující prostředky:  
  
-   Soubor atom.xml díky rozšíření k dispozici jako privátní galerie. Informace o tom, jak připojit soubor atom.xml **rozšíření a aktualizace**, naleznete v tématu [privátní Galerie](../extensibility/private-galleries.md).  
  
-   Složka, která obsahuje všechny soubory obrázků, které se extrahují z rozšíření (například snímky obrazovky). Soubor atom.xml obsahuje relativní odkazy na tyto Image tak, aby byly k dispozici v **rozšíření a aktualizace**.  
  
 Předpokládejme například, že jste shromáždili následující dvě rozšíření do složky:  
  
-   Template_Wizard_239.VSIX, což je prázdná šablona projektu VSIX.  
  
-   SelectionHighlight.vsix, což je nástroj, zvýrazněte všechny instance vybrané aplikace Word.  
  
 Obsah souboru atom.xml by vypadat podobně jako v následujícím příkladu:  
  
```  
  <?xml version="1.0" encoding="utf-8" ?>   
- <feed xmlns="http://www.w3.org/2005/Atom">  
  <title type="text" />   
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>   
  <updated>2011-04-14T21:25:48Z</updated>   
- <entry>  
  <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>   
  <title type="text">Highlight all occurrences of selected word</title>   
  <summary type="text">This extends the editor to highlight ….</summary>   
  <published>2011-04-14T14:24:51-07:00</published>   
  <updated>2011-04-14T14:24:22-07:00</updated>   
- <author>  
  <name>Microsoft</name>   
  </author>  
  <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />   
  <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />   
  <content type="application/octet-stream" src="SelectionHighlight.vsix" />   
- <Vsix xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010">  
  <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>   
  <Version>1.31</Version>   
  <References />   
  <Rating xsi:nil="true" />   
  <RatingCount xsi:nil="true" />   
  <DownloadCount xsi:nil="true" />   
  </Vsix>  
  </entry>  
- <entry>  
  <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>   
  …  
  </entry>  
  </feed>  
  
```  
  
 Všimněte si, že dvě značky odkazu odkazovat na snímky obrazovky v generovanou složku Obrázky.  
  
## <a name="see-also"></a>Viz také  
 [Privátní galerie](../extensibility/private-galleries.md)

