---
title: Šifrování a zalomení řádků | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 88f04720610bad5064f7f9d7a43beef2410b045f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787463"
---
# <a name="encodings-and-line-breaks"></a>Šifrování a zalomení řádků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V sadě Visual Studio můžete použít **souboru/pokročilé nastavení uložení** má nastavení k určení typu zalomení řádku znaků. Můžete také změnit kódování souboru se stejným nastavením.  
  
> [!NOTE]
>  Pokud máte určité typy nastavení vývoje (Visual Basic, F#, vývoj pro Web) nemusí zobrazit **pokročilé nastavení uložení** v nabídce. Chcete-li změnit nastavení (například se běžných), otevřete **nástroje / Import a Export nastavení**. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 V sadě Visual Studio tyto znaky jsou interpretovány jako konce řádků:  
  
- CRLF: Návrat na začátek + LF, znaky Unicode 000 D + 000A  
  
- LF: LF, znak Unicode 000A  
  
- NASTAVIT: Další řádek znak Unicode 0085  
  
- LS: Oddělovač řádků, znak Unicode 2028  
  
- PS: Oddělovač odstavců, znak Unicode 2029  
  
  Text, který se zkopíruje z jiné aplikace udržuje původní kódování a znaky konce řádku. Například při kopírování textu z programu Poznámkový blok a vložte ho do textového souboru v sadě Visual Studio, text má stejné nastavení, jako v poznámkovém bloku.  
  
  Při otevření souboru obsahujícího znaky konce řádku různých, může se zobrazit dialogové okno s dotazem, zda by měly být normalizovány znaky konců řádků nekonzistentní a jaký typ konců řádku vyberte.
