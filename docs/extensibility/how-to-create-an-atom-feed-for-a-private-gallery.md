---
title: 'Postupy: vytvoření Atom pro galerii privátní | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc39e4d11d826741239f11f62955fa4d2fb167cb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127474"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Postupy: vytvoření Atom pro galerii privátní
Můžete vytvořit kanál Atom (RSS) k z intranetového umístění, která obsahuje rozšíření a přidat informační kanál a **rozšíření a aktualizace** jako privátní galerie. Další informace najdete v tématu [privátní Galerie](../extensibility/private-galleries.md).  
  
## <a name="creating-an-atom-feed"></a>Vytvoření Atom kanálu  
 K vytvoření informačního kanálu jako privátní Galerie Atom, nejprve shromážděte rozšíření (VSIX soubory) do složky. Můžete je uspořádat do podsložky podle potřeby. Budete také potřebovat následující prostředky:  
  
-   Soubor atom.xml, který zpřístupní rozšíření jako privátní galerie. Informace o tom, jak připojit soubor atom.xml **rozšíření a aktualizace**, najdete v části [privátní Galerie](../extensibility/private-galleries.md).  
  
-   Složka, která obsahuje všechny soubory bitové kopie, které se extrahují z rozšíření (například snímky obrazovky). Soubor atom.xml obsahuje relativní odkazy na tyto bitové kopie, aby byly k dispozici v **rozšíření a aktualizace**.  
  
 Předpokládejme například, že jste shromáždili následující dvě rozšíření do složky:  
  
-   Template_Wizard_239.VSIX, což je prázdné šablony projektu VSIX.  
  
-   SelectionHighlight.vsix, což je nástroj, abyste měli na očích všechny výskyty vybrané aplikace word.  
  
 Obsah souboru atom.xml by podobat následujícímu příkladu:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
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
<Vsix xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010">  
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
  
 Všimněte si, že jsou obě značky odkazu odkazovat na snímky obrazovky ve složce generovaného bitových kopií.  
  
## <a name="see-also"></a>Viz také  
 [Privátní galerie](../extensibility/private-galleries.md)
