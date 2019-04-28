---
title: Vytvoření schématu XML
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e93155f230ee4a564116f5d1357a97923706c36
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62783490"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Postupy: Vytvoření schématu XML z dokumentu XML

XML editor umožňuje vytvářet jazyk (XSD) schématu definice schématu XML z dokumentu XML. Soubor XML určuje způsob generování schématu následujícím způsobem:

- Pokud dokument XML nemá žádné schéma nebo dokumentu typ definice (DTD) s ním spojená, data v dokumentu XML je použít k odvození nové schéma XML.

- Obsahuje-li dokumentu XML přidružené DTD, externí specifikaci DTD a interní podmnožinu se převedou na odpovídající schématu XML.

- Pokud dokument XML obsahuje vložené schéma XML-Data Reduced (XDR), schéma XDR je převést na odpovídající schématu XML.

Schémata, které jsou vytvořeny se použije k poskytnutí technologie IntelliSense pro soubor XML.

Další informace o modulu odvození schématu najdete v tématu [odvození schématu XML](/dotnet/standard/data/xml/inferring-an-xml-schema).

## <a name="to-create-an-xml-schema"></a>Vytvoření schématu XML

1. Otevřete soubor XML v sadě Visual Studio.

2. V panelu nabídky zvolte **XML** > **Create Schema**.

   Dokument schématu XML je vytvořen a otevřen pro každý obor názvů v souboru XML. Každý schématu je otevřen jako dočasný soubor různé. Schémata můžete uložit na disk, přidány do projektu nebo zahozeny.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)