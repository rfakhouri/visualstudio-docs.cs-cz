---
title: "Visual Studio kódování a konce znaků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b6afbc9ca8f93dcb0313c70a9d1e41579a6bf31f
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="encodings-and-line-breaks"></a>Šifrování a zalomení řádků
Následující znaky se interpretují jako zalomení řádků v sadě Visual Studio:  
  
-   Znaky CR LF: CR + řádku kanálu, 000 D + 000A znaky kódování Unicode  
  
-   LF: Informační kanál, znak Unicode 000A řádku  
  
-   Nastavit: Další řádek znak Unicode 0085  
  
-   LS: Oddělovač řádků, znak Unicode 2028  
  
-   PS: Oddělovač odstavců, znak Unicode 2029  
  
Text, který se zkopíruje z jiných aplikací zachová původní kódování a znaky konce řádku. Například při kopírování textu z Poznámkový blok a vložte ho do textového souboru v sadě Visual Studio, text má stejné nastavení, které měl v poznámkovém bloku.  
  
Otevřete soubor, který má znaky konce řádku jiný, zobrazí se dialogové okno s dotazem, zda by měl být normalized znaky konců řádků nekonzistentní, jaký typ řádku konce a vybrat.

Můžete použít **soubor**, **rozšířené možnosti ukládání** dialogové okno k určení typu chcete znaky konce řádku. Můžete také změnit kódování souboru se stejným nastavením.

![Dialogové okno pokročilé možnosti Uložit](media/line_endings.png)
  
> [!NOTE]
>  Pokud nevidíte **rozšířené možnosti ukládání** na **souboru** nabídky, které chcete přidat. Zvolte **nástroje**, **přizpůsobit...** a potom zvolte **příkazy** kartě. V **řádku nabídek** rozevíracího seznamu vyberte **soubor**, zvolte **příkaz Přidat...**  tlačítko. V **přidejte příkaz** dialogovém **kategorie**, zvolte **soubor**a potom v **příkazy** vyberte  **Rozšířené možnosti ukládání...** . Zvolte **OK** a potom zvolte **přesunout dolů** tlačítko příkaz přesunout na libovolné místo v nabídce. Zvolte **zavřete** zavřete **přizpůsobit** dialogové okno. Další informace najdete v tématu [přizpůsobení nabídek a panelů nástrojů](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md#customizing_menu).

Alternativně můžete přístup **rozšířené možnosti ukládání** dialogové okno a vybrat **soubor**, **Uložit \<soubor\> jako...** . V **uložit soubor jako** dialogovém okně vyberte trojúhelníček rozevíracího seznamu vedle položky **Uložit** tlačítko a zvolte **uložit s kódováním...** .

## <a name="see-also"></a>Viz také
[Psaní kódu v editoru](../ide/writing-code-in-the-code-and-text-editor.md)