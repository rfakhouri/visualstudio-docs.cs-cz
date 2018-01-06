---
title: "Postupy: lokalizace kódu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- localizing code [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
ms.assetid: 0e852052-5ad4-4517-81cf-8865ec304441
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4e920074f6f771c2b8e5a78b128bf3b1f096d77e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-localize-code"></a>Postupy: Lokalizace kódu
  Nelokalizované kód používá pevně zakódovaný řetězcové hodnoty. Na kód řetězce pro lokalizaci, je nahradit volání <xref:System.Web.HttpContext.GetGlobalResourceObject%2A>, což je metoda, která odkazuje na lokalizované prostředky.  
  
## <a name="localizing-code"></a>Lokalizace kódu  
  
#### <a name="to-localize-code"></a>Chcete-li lokalizace kódu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro položku projektu a potom zvolte **přidat**, **modulu**.  
  
     Vyberte **souboru prostředků** šablony.  
  
    > [!NOTE]  
    >  Ujistěte se, že soubor prostředků přidat do položky projektu služby SharePoint, aby vlastnost typ nasazení k dispozici. Tato vlastnost se vyžaduje později v tomto postupu.  
  
2.  Zadejte název zvoleného spolu s příponou RESX, jako je například MyAppResources.resx souboru prostředků jazyka výchozí.  
  
3.  Opakujte kroky 1 a 2, pokud chcete přidat soubory samostatné prostředků do položky projektu služby SharePoint: jeden pro každou lokalizované jazyk.  
  
     Použijte stejný základní název pro každý soubor lokalizovaný prostředek, ale přidat ID jazykovou verzi. Například název němčině lokalizovaný prostředek MyAppResources.de DE.resx.  
  
4.  Otevřete soubor každý prostředek a přidejte lokalizované řetězce. Použijte stejný řetězec ID do každého souboru.  
  
5.  Změňte hodnotu **typ nasazení** vlastnost souborů prostředků se **AppGlobalResource** způsobí každý soubor pro nasazení do složky App_GlobalResources serveru.  
  
6.  Ponechte hodnotu **akce sestavení** vlastnosti každého souboru jako **vložený prostředek**.  
  
     Vložené prostředky jsou zkompilovány do projektu knihovny DLL.  
  
7.  Sestavte projekt a vytvořte prostředek satelitní knihovny DLL.  
  
8.  V **návrháře balíčků**, vyberte **Upřesnit** a pak přidejte satelitní sestavení.  
  
9. V **umístění** pole, předřazení ID složku jazykovou verzi pro cestu k umístění, jako je například de-DE\\*název položky projektu*. resources.dll.  
  
10. Pokud vaše řešení neodkazuje již System.Web sestavení, přidejte odkaz na jeho a přidejte direktivu ve svém kódu pro <xref:System.Web>.  
  
11. Vyhledejte všechny řetězce pevně zakódovaná ve vašem kódu, které jsou viditelné pro uživatele, například textu uživatelského rozhraní, chyb a text zprávy. Nahraďte volání <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> metoda pomocí následující syntaxe:  
  
    ```  
    HttpContext.GetGlobalResourceObject("Resource File Name", "String ID")  
    ```  
  
12. Zvolte klávesy F5 sestavení a spuštění aplikace.  
  
13. Ve službě SharePoint změňte z výchozí jazyk zobrazení.  
  
     Lokalizované řetězce se zobrazí v aplikaci. Pokud chcete zobrazit lokalizované prostředky, musí mít serveru SharePoint jazyková sada nainstalovaná odpovídající jazykové verze souboru prostředků.  
  
## <a name="see-also"></a>Viz také  
 [Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)   
 [Postupy: lokalizace funkce](../sharepoint/how-to-localize-a-feature.md)   
 [Postupy: lokalizace značek ASPX](../sharepoint/how-to-localize-aspx-markup.md)   
 [Postupy: Přidání zdrojového souboru](../sharepoint/how-to-add-a-resource-file.md)  
  
  