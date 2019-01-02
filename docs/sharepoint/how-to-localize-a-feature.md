---
title: 'Postupy: Lokalizace funkce | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- features [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 165eee357c001720af132236a8577f259efa4f24
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53887671"
---
# <a name="how-to-localize-a-feature"></a>Postupy: Lokalizace funkce
  Ve výchozím nastavení použijte funkci názvy a popisy pevně zakódované řetězcové hodnoty. Chcete-li lokalizovat funkci nadpis a popis, nahraďte řetězce výrazy, které odkazují na lokalizované prostředky.  
  
## <a name="localize-a-feature"></a>Lokalizace funkce  
  
#### <a name="to-localize-a-feature"></a>Chcete-li lokalizovat funkci  
  
1.  V **Průzkumníka řešení**, otevřete místní nabídku **Feature1** uzel a klikněte na tlačítko **přidat prostředek funkce**.  
  
2.  V **přidat prostředek** dialogového okna zvolte **neutrální jazyk** ze seznamu jako jazykovou verzi pro soubor prostředků výchozího jazyka funkce.  
  
3.  Předchozí krok opakujte pro každý lokalizovaný jazyk, volba jazyků podle vašeho výběru pro funkci lokalizované soubory prostředků.  
  
     Soubory prostředků samostatné funkce jsou vytvořeny: jeden pro výchozí jazyk a jeden pro každý lokalizovaný jazyk, který chcete podporovat.  
  
4.  Otevřete každý soubor prostředků v editoru prostředků a potom zadejte všechny identifikátory řetězce a jejich hodnot.  
  
     Například v souboru prostředků výchozí funkci, zadejte ID řetězce **Title** s hodnotou **můj název funkce**, a druhý řetězec ID **popis** s hodnotou **Popis pro moje funkce**. Pro každý lokalizovaný soubor prostředků použijte stejná ID používaných pro výchozí funkce prostředek řetězce, ale zadat lokalizované řetězce pro hodnoty.  
  
5.  Po zadání všech hodnot prostředků, otevřete místní nabídku pro funkci (například *Feature1.feature*) a klikněte na tlačítko **Návrhář zobrazení** funkci Otevřít v Návrháři funkce.  
  
6.  Chcete-li lokalizovat **Title** a **popis** pole ve funkci, zadejte hodnoty do jejich polí použijte následující formát:  
  
     `$Resources:` *Identifikátor řetězce*  
  
     Zadejte například $Resources:**Title** v **název funkce** pole a $Resources:**popis** v **popis funkce** pole .  
  
     Řetězec ID musí odpovídat těm, které se používají v souborech prostředků.  
  
7.  Zvolte **F5** klíče pro sestavení a spuštění aplikace.  
  
8.  V Sharepointu, otevřete **Akce webu** nabídce zvolte **nastavení webu**a pak na **Akce webu** zvolte **spravovat funkce webu** odkaz.  
  
9. Ve službě SharePoint změňte jazyk zobrazení z výchozího.  
  
     Funkce lokalizovaný název a popis se zobrazí v aplikaci. Chcete-li zobrazit lokalizované prostředky, musí mít SharePoint server nainstalovanou jazykovou sadu odpovídající jazykové verzi souboru prostředků.  
  
## <a name="see-also"></a>Viz také:
 [Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)   
 [Postupy: Přidejte soubor prostředků](../sharepoint/how-to-add-a-resource-file.md)   
 [Postupy: Lokalizace značek ASPX](../sharepoint/how-to-localize-aspx-markup.md)   
 [Postupy: Lokalizace kódu](../sharepoint/how-to-localize-code.md)  
