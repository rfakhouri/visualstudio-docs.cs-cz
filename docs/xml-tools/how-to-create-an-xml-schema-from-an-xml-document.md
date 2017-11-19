---
title: "Postupy: vytvoření schématu XML z dokumentu XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 811107d3eb5c2c9c974b3d01041bcc9d1bdcbbc9
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Postupy: vytvoření schématu XML z dokumentu XML
Editor souborů XML umožňuje vytvořit schéma schématu XML definition language (XSD) z dokumentu XML. Instance dokumentu XML určuje způsob generování schématu následujícím způsobem:  
  
-   Pokud v dokumentu XML se žádné schéma nebo s ním spojená dokumentu typ definice (DTD), data v dokumentu XML slouží k odvození nové schéma XML.  
  
-   Pokud v dokumentu XML obsahuje přidružené DTD, externí DTD a vnitřní podmnožiny se převedou na odpovídající schématu XML.  
  
-   Pokud v dokumentu XML obsahuje vložené schéma XML-Data Reduced (XDR), schématu XDR jsou převedeny na odpovídající schématu XML.  
  
Schémata, které jsou vytvořené pak lze poskytovat technologii IntelliSense pro dokument XML.  
  
Další informace o schématu odvozovacím modulu najdete v tématu [odvození schématu XML](/dotnet/standard/data/xml/inferring-an-xml-schema).  
  
### <a name="to-create-an-xml-schema"></a>Chcete-li vytvořit schéma XML  
  
1.  Načtení instance dokumentu XML do editoru XML.  
  
2.  Klikněte **Create Schema** tlačítko z **nástrojů**.  
  
     Dokument schématu XML je vytvořen a otevřít pro každý obor názvů nalezen v dokumentu XML instance. Každý schématu je otevřen jako soubor různé dočasné.  
  
     Schémata můžete uložit na disk, přidat do projektu nebo zahozeny.  
  
    > [!NOTE]
    >  **Create Schema** je k dispozici v místní nabídce editoru XML a v části také **XML** nabídky.  
  
## <a name="see-also"></a>Viz také  
 [XML Editor](../xml-tools/xml-editor.md)