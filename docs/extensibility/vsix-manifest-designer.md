---
title: "Návrhář manifestu VSIX | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.Sdk.VsixManifestEditor
helpviewer_keywords:
- vsixmanifest
- vsix manifest
- manifest designer
ms.assetid: 5a691e77-cf91-430d-90ea-361d9031ef83
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eaf35854aede65b605b4578ca9ee71375ad7a479
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsix-manifest-designer"></a>Návrhář manifestu VSIX
Upravuje soubor manifestu balíčku VSIX, který nastaví chování při instalaci pro rozšíření sady Visual Studio.  
  
 **Návrhář manifestu VSIX** se mapuje na schéma základní VSIX. Každý element ve schématu můžete nastavit pomocí prvku odpovídající v návrháři. Další informace o schématu najdete v tématu [referenční informace o VSIX rozšíření schématu 2.0](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
 Chcete-li otevřít **Návrhář manifestu VSIX**, vyhledejte soubor source.extension.vsixmanifest v **Průzkumníku řešení**a otevřete soubor. Pokud soubor neobsahuje platný kód XML, nebude otevřete návrháře manifestu.  
  
> [!NOTE]
>  Source.extension.vsixmanifest je výstup do extension.vsixmanifest, když je balíček vytvořen.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Návrhář manifestu VSIX** obsahuje čtyři oddíly, které odpovídají k těmto prvkům nejvyšší úrovně schématu:  
  
-   Metadata  
  
-   Nainstalujte cíle  
  
-   Prostředky  
  
-   Závislosti  
  
 Oblasti záhlaví obsahuje následující ovládací prvky.  
  
 **Název produktu**  
 Popisuje název rozšíření.  
  
 **ID produktu**  
 Určuje jedinečné identifikační informace pro tento balíček.  
  
 **Autor**  
 Určuje jméno autora rozšíření.  
  
 **Verze**  
 Určuje číslo verze rozšíření.  
  
 **Metadata** karta obsahuje následující ovládací prvky.  
  
 **Popis**  
 Poskytuje textový popis přípony, který se má zobrazit v **Správce rozšíření**.  
  
 **Jazyk**  
 Určuje výchozí jazyk pro balíček, který odpovídá textových dat v manifestu. `Language` Atribut konvenci, běžné language runtime (CLR) národního prostředí kód pro sestavení prostředků, například en-us, en, fr-fr. Výchozí hodnota je neutrální; To znamená, že balíček bude spouštět všechny jazykové verze sady Visual Studio.  
  
 **Licence**  
 Určuje textový soubor, který obsahuje uživatelskou licenci, pokud je k dispozici.  
  
 **Ikona**  
 Určuje soubor grafiky (PNG, BMP, .jpeg, .ico), který obsahuje ikonu, která se zobrazí v **Správce rozšíření**, pokud se nachází na ikonu. Obrázek ikony musí být 32 x 32 pixelů nebo bude nastavena velikost do těchto dimenzí. Pokud není určena žádná ikona, **Správce rozšíření** používá výchozí ikonu.  
  
 **Náhled obrázku**  
 Určuje soubor grafiky (PNG, BMP, .jpeg, .ico), který obsahuje obrázek náhledu, který se má zobrazit v **Správce rozšíření**, pokud je k dispozici náhled obrázku. Náhled obrázku musí být 200 x 200 pixelů. Pokud není zadaný žádný obrázek náhledu, **Správce rozšíření** používá výchozí image.  
  
 **Značky**  
 Přidá text značky se mají použít pro tipy pro hledání.  
  
 **Zpráva k vydání verze**  
 Určuje soubor (.txt, .rtf), který obsahuje poznámky k verzi. Také přebírá adresu URL webu, který se zobrazí v poznámkách k verzi.  
  
 **Příručka Začínáme**  
 Určuje soubor (.txt, .rtf), který obsahuje informace o tom, jak používat rozšíření nebo obsah v balíčku VSIX. Tento průvodce se zobrazí po dokončení instalace rozšíření. Také přebírá adresu URL webu, který se zobrazí v průvodci.  
  
 **Další informace o adrese URL**  
 Určuje adresu URL webu, který obsahuje další informace o produktu.  
  
 **Nainstalovat cíle** karta obsahuje následující ovládací prvky.  
  
 **Typ instalace**  
 Uvádí **rozšíření sady Visual Studio** a **Extension SDK** jako cíl typy instalace. Možnosti lišit v závislosti na typu, který zvolíte.  
  
 **Rozšíření sady Visual Studio**  
 Uvádí **InstallationTarget** elementy, které popisují, jak lze nainstalovat balíček a do které produkty Visual Studio lze nainstalovat toto rozšíření. Každý produkt je určen samostatně název a verze nebo verze rozsahu.  Produkty můžete do seznamu přidat, upravit a odstranit. Název a verzi produktu odpovídá **Id** a **verze** atributy přidruženého **InstallationTarget** element.  
  
 **Rozsah verze** je [12,0, 14,0] a používá následující zápis:  
  
-   [-minimální verze (včetně).  
  
-   ]-maximální verze (včetně).  
  
-   (-výhradní minimální verze  
  
-   )-maximální verze výhradní  
  
-   Jedna verze # - jenom určená verze  
  
 **Rozšíření sady SDK**  
 Určuje globální instalace, která není v oboru konkrétním produktu a verze. **Cílové platformy identifikátor** je platforma, jako je například "Windows", který jste cílení. **Cílová verze platformy** je verze, jako je například 8.0 cílové platformy. **Název SDK** a **verze sady SDK** jsou název a číslo verze sady SDK, v uvedeném pořadí.  
  
 **Tato VSIX je instalována pro všechny uživatele (vyžaduje zvýšení oprávnění na instalaci)** zaškrtávací políčko  
 Pokud je toto políčko zaškrtnuto, toto rozšíření je nainstalován pro všechny uživatele; jinak je nainstalována pouze pro aktuálního uživatele.  
  
 **Instalační služba systému Windows je nainstalován tento VSIX** zaškrtávací políčko  
 Pokud je toto políčko zaškrtnuto, toto rozšíření je nainstalována Instalační služba systému Windows (soubor MSI); jinak se instaluje jako typického balíčku VSIX (soubor VSIX).  
  
 **Prostředky** karta obsahuje následující ovládací prvky.  
  
 **Seznam prostředků**  
 Uvádí Asset prvky, které popisují prvky rozšíření nebo obsahu které tento balíček ploch. Každé rozšíření nebo obsahu elementu je uvedené odděleně podle zdroje, typ a cestu. Elementy rozšíření a obsah můžete do seznamu přidat, upravit a odstranit. Typ a cestu rozšíření nebo obsah elementu odpovídá `Type` a `Path` atributy přidruženého `Asset` elementu. Jsou známé následující typy:  
  
-   Microsoft.VisualStudio.Package  
  
-   Microsoft.VisualStudio.MefComponent  
  
-   Microsoft.VisualStudio.ToolboxControl  
  
-   Microsoft.VisualStudio.Samples  
  
-   Microsoft.VisualStudio.ProjectTemplate  
  
-   Microsoft.VisualStudio.ItemTemplate  
  
-   Microsoft.VisualStudio.Assembly  
  
-   Microsoft.ExtensionSDK  
  
 Můžete přidat nebo upravit prostředek, musíte zadat typ prostředku, jestli asset na projekt v aktuálním řešení, nebo soubor v systému souborů a název projektu. Můžete také zadat název složky, do níž má být vložen.  
  
 Můžete také vytvořit vlastní typy a přiřadit jim jedinečné názvy.  
  
 **Závislosti** karta obsahuje následující ovládací prvky.  
  
 **Název zdroje a rozsahu verze.**  
 Obsahuje seznam závislostí elementy tohoto balíčku, na které jsou i další balíčky, které tento balíček závisí na. Pokud je zadaná závislost balíčku, musí být nainstalována před instalací tohoto balíčku; Tento balíček jinak, nainstalujte ji.  
  
 Závislost balíčky jsou zadaný identifikátor, název, verze rozsah, zdroje a jak se závislost možné přeložit. Každý balíček závislostí je uvedené odděleně podle název, verzi a zdroj. Závislosti balíčků můžete do seznamu přidat, upravit a odstranit.  
  
 Identifikátor se musí shodovat `ID` atribut metadat závislost balíčku. Zdrojem může být na projekt v aktuálním řešení, aktuálně nainstalovaná rozšíření nebo souboru. **Jak je vyřešit závislosti** nastavení může být relativní cesta vnořené balíčku nebo adresu URL umístění stahování pro závislost. ID, verzi a překlad závislost balíčku odpovídají `Id`, `Version`, a `Location` atributy přidruženého `Dependency` elementu.  
  
## <a name="see-also"></a>Viz také  
 [VSIX rozšíření schéma 2.0 – referenční informace](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)