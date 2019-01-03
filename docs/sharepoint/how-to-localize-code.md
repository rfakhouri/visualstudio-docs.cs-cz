---
title: 'Postupy: Lokalizace kódu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- localizing code [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9f45ef99210ccf5e6caa22e4aef6ba303aa6a6b2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990789"
---
# <a name="how-to-localize-code"></a>Postupy: Lokalizace kódu
  Nelokalizovaný kód používá pevně zakódované řetězcové hodnoty. Chcete-li lokalizovat řetězce kódu, nahraďte je voláními do <xref:System.Web.HttpContext.GetGlobalResourceObject%2A>, což je metoda, která odkazuje na lokalizované prostředky.  
  
## <a name="localize-code"></a>Lokalizace kódu  
  
#### <a name="to-localize-code"></a>Chcete-li lokalizovat kód  
  
1.  V **Průzkumníka řešení**, otevřete místní nabídku pro položku projektu a klikněte na tlačítko **přidat** > **modulu**.  
  
     Zvolte **soubor prostředků** šablony.  
  
    > [!NOTE]  
    >  Nezapomeňte přidat soubor prostředků do položky projektu SharePoint tak, aby vlastnost typ nasazení je k dispozici. Tato vlastnost je vyžadováno později v tomto postupu.  
  
2.  Pojmenujte soubor prostředků výchozího jazyka jméno dle vašeho výběru s *RESX* rozšíření, jako například *MyAppResources.resx*.  
  
3.  Opakujte kroky 1 a 2 pro přidání souborů prostředků do položky projektu služby SharePoint: jeden pro každý lokalizovaný jazyk.  
  
     Použijte stejný základní název pro každý lokalizovaný soubor prostředků, ale přidejte identifikátor jazykové verze. Například pojmenujte německý lokalizovaný prostředek *MyAppResources.de-DE.resx*.  
  
4.  Otevřete každý soubor prostředků a přidejte lokalizované řetězce. V každém souboru použijte stejná ID řetězce.  
  
5.  Změňte hodnotu **typ nasazení** vlastnosti každého souboru prostředků na **AppGlobalResource** pro každý soubor pro nasazení do složky App_GlobalResources serveru.  
  
6.  Ponechte hodnotu **akce sestavení** jednotlivých souborů jako **integrovaný prostředek**.  
  
     Vložené prostředky jsou kompilovány do projektu knihovny DLL.  
  
7.  Vytvoření projektu pro vytvoření prostředku satelitní knihovny DLL.  
  
8.  V **návrháři balíčku**, zvolte **Upřesnit** kartu a pak přidejte satelitní sestavení.  
  
9. V **umístění** pole, předřaďte proveďte předřazení složky ID pro cestu k umístění, jako například *de-DE\\\<název položky projektu >. resources.dll*.  
  
10. Pokud vaše řešení již neobsahuje odkaz na sestavení System.Web, přidejte na ni odkaz a přidejte direktivu ve vašem kódu k <xref:System.Web>.  
  
11. Vyhledejte všechny pevně zakódované řetězce v kódu, které jsou viditelné pro uživatele, jako je text zprávy, chyby a text uživatelského rozhraní. Nahraďte volání <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> metodu pomocí následující syntaxe:  
  
    ```csharp  
    HttpContext.GetGlobalResourceObject("Resource File Name", "String ID")  
    ```  
  
12. Zvolte **F5** klíče pro sestavení a spuštění aplikace.  
  
13. Ve službě SharePoint změňte jazyk zobrazení z výchozího.  
  
     Lokalizované řetězce jsou zobrazeny v aplikaci. Chcete-li zobrazit lokalizované prostředky, musí mít SharePoint server nainstalovanou jazykovou sadu odpovídající jazykové verzi souboru prostředků.  
  
## <a name="see-also"></a>Viz také:
 [Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)   
 [Postupy: Lokalizace funkce](../sharepoint/how-to-localize-a-feature.md)   
 [Postupy: Lokalizace značek ASPX](../sharepoint/how-to-localize-aspx-markup.md)   
 [Postupy: Přidejte soubor prostředků](../sharepoint/how-to-add-a-resource-file.md)  
