---
title: 'Postupy: Vytvoření schématu XML z dokumentu XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 629519a6df8c570ee806ec7360e03f442042b5ba
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915202"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Postupy: Vytvoření schématu XML z dokumentu XML

Editor souborů XML můžete vytvořit jazyk (XSD) schématu definice schématu XML z dokumentu XML. Instance dokumentu XML určuje způsob generování schématu následujícím způsobem:

-   Pokud dokument XML nemá žádné schéma nebo dokumentu typ definice (DTD) s ním spojená, data v dokumentu XML je použít k odvození nové schéma XML.

-   Obsahuje-li dokumentu XML přidružené DTD, externí specifikaci DTD a interní podmnožinu se převedou na odpovídající schématu XML.

-   Pokud dokument XML obsahuje vložené schéma XML-Data Reduced (XDR), schéma XDR je převést na odpovídající schématu XML.

Schémata, které jsou vytvořeny se použije k poskytnutí technologie IntelliSense pro dokument XML.

Další informace o modulu odvození schématu najdete v tématu [odvození schématu XML](/dotnet/standard/data/xml/inferring-an-xml-schema).

## <a name="to-create-an-xml-schema"></a>Vytvoření schématu XML

1.  Načtěte instanci dokumentu XML do editoru XML.

2.  Klikněte na tlačítko **Create Schema** tlačítko **nástrojů**.

     Dokument schématu XML je vytvořen a otevřen pro každý obor názvů v dokumentu instance XML. Každý schématu je otevřen jako dočasný soubor různé.

     Schémata můžete uložit na disk, přidány do projektu nebo zahozeny.

    > [!NOTE]
    >  **Create Schema** příkaz je také k dispozici v místní nabídce editoru XML a v části **XML** nabídky.

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)