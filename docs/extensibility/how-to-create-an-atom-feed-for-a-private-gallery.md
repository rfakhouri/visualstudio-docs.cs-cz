---
title: 'Postupy: Vytvoření Atom pro privátní galerii | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d6053c01908df9f1c2884e81c8610a989ac89294
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55030675"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Postupy: Vytvoření Atom pro privátní galerii
Můžete vytvořit kanál Atom (RSS) do umístění v intranetu, která obsahuje rozšíření a přidání informačního kanálu do **rozšíření a aktualizace** jako privátní galerie. Další informace najdete v tématu [privátní Galerie](../extensibility/private-galleries.md).  
  
## <a name="create-an-atom-feed"></a>Vytvoření informačního kanálu Atom  
 Vytvořit jako soukromou galerii informačního kanálu Atom, nejdřív shromáždit vaše rozšíření (*VSIX* souborů) do složky. Můžete je uspořádat do podsložky potřebujete. Budete také potřebovat následující prostředky:  
  
- *Atom.xml* soubor, který zpřístupňuje rozšíření jako privátní galerie. Informace o tom, jak se připojit *atom.xml* do souboru **rozšíření a aktualizace**, naleznete v tématu [privátní Galerie](../extensibility/private-galleries.md).  
  
- Složka, která obsahuje všechny soubory obrázků, které se extrahují z rozšíření (například snímky obrazovky). *Atom.xml* soubor obsahuje relativní odkazy na tyto Image tak, aby byly k dispozici v **rozšíření a aktualizace**.  
  
  Předpokládejme například, že jste shromáždili následující dvě rozšíření do složky:  
  
- *Template_Wizard_239.VSIX*, což je prázdná šablona projektu VSIX.  
  
- *SelectionHighlight.vsix*, což je nástroj, který zvýraznit všechny výskyty vybrané aplikace word.  
  
  Obsah *atom.xml* soubor bude vypadat podobně jako v následujícím příkladu:  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">
  <title type="text" />
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>
  <updated>2011-04-14T21:25:48Z</updated>
  <entry>
    <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>
    <title type="text">Highlight all occurrences of selected word</title>
    <summary type="text">This extends the editor to highlight ....</summary>
    <published>2011-04-14T14:24:51-07:00</published>
    <updated>2011-04-14T14:24:22-07:00</updated>
    <author>
      <name>Microsoft</name>
    </author>
    <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />
    <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />
    <content type="application/octet-stream" src="SelectionHighlight.vsix" />
    <Vsix xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>
      <Version>1.31</Version>
      <References />
      <Rating xsi:nil="true" />
      <RatingCount xsi:nil="true" />
      <DownloadCount xsi:nil="true" />
    </Vsix>
  </entry>
  <entry>
    <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>
    ...
  </entry>
</feed>
```  
  
 Všimněte si, že dvě značky odkazu odkazovat na snímky obrazovky v generovanou složku Obrázky.  
  
## <a name="see-also"></a>Viz také:  
 [Privátní Galerie](../extensibility/private-galleries.md)
