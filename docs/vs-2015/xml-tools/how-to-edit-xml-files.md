---
title: 'Postupy: Úprava souborů XML | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7bb1e8803a133a85af129a6e929428aae89acaa6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678700"
---
# <a name="how-to-edit-xml-files"></a>Postupy: Úprava souborů XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: Úprava souborů XML](https://docs.microsoft.com/visualstudio/xml-tools/how-to-edit-xml-files).  
  
  
XML Editor je nový editor souborů XML. Můžete použít samostatný soubor XML nebo soubor přidružený k projektu sady Visual Studio. XML Editor souvisí s následujícími příponami: .config, DTD, .xml, XSD, .xdr, XSL, XSLT a .vssettings. XML Editor je také přidružen jiný soubor typ, který nemá žádné konkrétní editor zaregistrovaný, a který obsahuje obsah XML nebo DTD.  
  
> [!NOTE]
>  XHTML dokumenty jsou zpracovány pomocí editoru jazyka HTML.  
  
### <a name="to-edit-an-xml-file"></a>Chcete-li upravit soubor XML  
  
1.  Poklikejte na soubor, který chcete upravit.  
  
### <a name="to-add-a-new-xml-file-to-a-project"></a>Chcete-li přidat nový soubor XML do projektu  
  
1.  Z **projektu** nabídce vyberte možnost **přidat novou položku**.  
  
2.  Vyberte **soubor XML** z **šablony** podokně.  
  
3.  Zadejte název souboru **název** pole a stiskněte klávesu **přidat**.  
  
     Soubor XML je přidán do projektu a otevřít v editoru XML. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8" ?>`.  
  
### <a name="to-add-an-existing-xml-file-to-a-project"></a>Chcete-li přidat k existujícímu souboru XML do projektu  
  
1.  Z **projektu** nabídce vyberte možnost **přidat existující položku**.  
  
     **Přidat existující položku** zobrazí se dialogové okno.  
  
2.  Vyberte soubor XML a stisknutím klávesy **přidat**.  
  
### <a name="to-create-a-new-xml-or-xslt-file"></a>Chcete-li vytvořit nový soubor XML nebo XSLT  
  
1.  Z **souboru** nabídce vyberte možnost **nový**.  
  
     **Nový soubor** zobrazí se dialogové okno.  
  
2.  Vyberte **soubor XML** a vytvořte nový soubor XML, nebo vyberte **soubor XSLT** k vytvoření nové šablony stylů XSLT.  
  
3.  Klikněte na tlačítko **otevřít**.  
  
### <a name="to-create-a-project-for-xml-files"></a>Vytvoření projektu pro soubory XML  
  
1.  Z **souboru** nabídce vyberte možnost **nový**a pak vyberte **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  Vyberte jazyk kódu podle vašeho výběru, vyberte **prázdný projekt**a klikněte na tlačítko **OK**.  
  
3.  Přidáte soubory XML do projektu.  
  
     XML Editor najde schémata, které přidáte do tohoto projektu a používá pro ověření a funkce IntelliSense v XML, schématu nebo soubory XSLT, které upravíte tento projekt je otevřený.  
  
## <a name="see-also"></a>Viz také  
 [XML Editor](../xml-tools/xml-editor.md)   
 [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)   
 [Postupy: Vytvoření schématu XML z dokumentu XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)



