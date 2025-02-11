---
title: 'Postupy: Vytvoření. Vsct soubor z existující. Soubor CTC | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating based on a .ctc file
ms.assetid: 700e80a4-c1e1-4178-af53-45e86dd2c08b
caps.latest.revision: 9
manager: jillfra
ms.openlocfilehash: 7b963436e9d968dd5ba3829e97d0fd0c52e49641
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443011"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Postupy: Vytvoření. Vsct soubor z existující. Soubor CTC
Můžete vytvořit souboru .vsct založený na formátu XML z existujícího souboru zdrojové tabulky .ctc příkazu. Díky tomu mohou využít výhod nového založený na formátu XML [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] formátu kompilátoru příkaz tabulky (VSCT).  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Vytvoření souboru .vsct ze souboru .ctc  
  
1. Získejte kopii souboru jazyka Perl.  
  
2. Získejte kopii souboru skriptu jazyka Perl ConvertCTCToVSCT.pl, obvykle nachází v  *\<Visual Studio SDK instalační_cesta >* \VisualStudioIntegration\Tools\bin složky.  
  
3. Získejte kopii souboru .ctc zdrojového souboru, který chcete převést.  
  
4. Soubory umístíte do stejného adresáře.  
  
5. V [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] okna příkazového řádku, přejděte do adresáře.  
  
6. Type  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     kde je název souboru .ctc PkgCmd.ctc a PkgCmd.vsct je název souboru .vsct, kterou chcete vytvořit.  
  
     Tím se vytvoří nový .vsct XML příkaz tabulky zdrojový soubor. Stejně jako jakýkoli jiný soubor .vsct, můžete pomocí Vsct.exe, kompilátor VSCT Zkompilujte soubor.  
  
    > [!NOTE]
    > Přeformátování komentáře XML, lze vylepšit čitelnost souboru .vsct.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření. Soubor Vsct](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)