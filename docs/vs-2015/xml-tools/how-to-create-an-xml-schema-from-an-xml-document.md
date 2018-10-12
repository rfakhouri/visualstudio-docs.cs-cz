---
title: 'Postupy: vytvoření schématu XML z dokumentu XML | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5d2e4cc78ee79502c4f2e10b2343fa0723006b3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49181263"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Postupy: vytvoření schématu XML z dokumentu XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Editor souborů XML můžete vytvořit jazyk (XSD) schématu definice schématu XML z dokumentu XML. Instance dokumentu XML určuje způsob generování schématu následujícím způsobem:  
  
-   Pokud dokument XML nemá žádné schéma nebo dokumentu typ definice (DTD) s ním spojená, data v dokumentu XML je použít k odvození nové schéma XML.  
  
-   Obsahuje-li dokumentu XML přidružené DTD, externí specifikaci DTD a interní podmnožinu se převedou na odpovídající schématu XML.  
  
-   Pokud dokument XML obsahuje vložené schéma XML-Data Reduced (XDR), schéma XDR je převést na odpovídající schématu XML.  
  
 Schémata, které jsou vytvořeny se použije k poskytnutí technologie IntelliSense pro dokument XML.  
  
 Další informace o modulu odvození schématu najdete v tématu [odvození schématu XML](http://msdn.microsoft.com/library/b18e7ffd-3c04-482d-9934-ba2f6a59b2c9).  
  
### <a name="to-create-an-xml-schema"></a>Vytvoření schématu XML  
  
1.  Načtěte instanci dokumentu XML do editoru XML.  
  
2.  Klikněte na tlačítko **Create Schema** tlačítko **nástrojů**.  
  
     Dokument schématu XML je vytvořen a otevřen pro každý obor názvů v dokumentu instance XML. Každý schématu je otevřen jako dočasný soubor různé.  
  
     Schémata můžete uložit na disk, přidány do projektu nebo zahozeny.  
  
    > [!NOTE]
    >  **Create Schema** příkaz je také k dispozici v místní nabídce editoru XML a v části **XML** nabídky.  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)



