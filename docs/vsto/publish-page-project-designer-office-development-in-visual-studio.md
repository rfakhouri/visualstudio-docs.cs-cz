---
title: "Publikovat stránku, Návrhář (vývoj pro Office v sadě Visual Studio) projektu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectProperties.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio]
- publishing, Office solutions
- Property Pages dialog box, Publish [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: d9cc3fa102c0552893c6f7859a256b7df26e3af5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="publish-page-project-designer-office-development-in-visual-studio"></a>Publikovat stranu, návrhář projektů (vývoj pro Office v sadě Visual Studio)
  **Publikovat** stránky **Návrhář projektu** slouží ke konfiguraci vlastností pro nasazení.  
  
 Pro přístup k této stránce, vyberte na projekt v **Průzkumníku řešení**a pak klikněte na **projektu** nabídce zvolte *Projectname* **vlastnosti** . Pokud **publikovat** stránka se nezobrazí, vyberte **publikovat** kartě.  
  
> [!NOTE]  
>  Můžete také nastavit umístění pro publikování v **Průvodci publikováním**. Další informace najdete v tématu [postupy: publikování aplikací ClickOnce pomocí řešení Office](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8).  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Publikování umístění složky (webový server, ftp server nebo cesta k souboru)**  
 Požadováno.  
  
 Publikování umístění složky je adresář, do které Visual Studio zkopíruje soubory řešení například manifesty, sestavení a další soubory z buildu. Musíte mít oprávnění k zápisu do tohoto adresáře.  
  
 Mezi možnosti patří místního počítače, sdílené složky UNC nebo webové stránky HTTP/HTTPS. Cesta může být místní (*c:\foldername\publishfolder*), relativní (*publikování\\*), nebo plně kvalifikovaný umístění (*\\\servername\foldername* nebo http://*servername/název_složky*).  
  
 Ve výchozím umístění pro publikování je *http://localhost/projectname/* Pokud máte nainstalovanou službu IIS, nebo adresáři publish\ v takovém případě ještě nainstalována služba IIS.  
  
 **Adresy URL instalace složky**  
 Volitelné.  
  
 Instalační složka adresa URL je adresáři, ze kterého koncový uživatel nainstaluje přizpůsobení. Je také cestu, která řešení bude používat ke kontrole aktualizací. Cesta může být stejný jako publikování umístění složky, ale to není povinné.  
  
 Mezi možnosti patří místního počítače, sdílené složky UNC nebo webové stránky HTTP/HTTPS. Cesta může být místní (*c:\foldername\publishfolder*), relativní (*publikování\\*), nebo plně kvalifikovaný umístění (*\\\servername\foldername* nebo http://*servername/název_složky*). Všechny umístění protokolu HTTP nebo HTTPS musí být vytvořeny s znaků US-ASCII. Znaky znakové sady Unicode nejsou podporovány.  
  
 Pokud cesta instalace je nastavena, přizpůsobení soubory musí být v tomto umístění pro uživatele k instalaci přizpůsobení. Umístění je třeba nastavit pouze v případě, že znáte umístění poslední nasazení.  
  
 Pokud instalační soubory v umístění relativně k dokumentu nebo instalační program, jako třeba s parametrem CD ponechte toto pole prázdné.  
  
 Tuto hodnotu lze přiřadit později správcem. Další informace najdete v tématu [postup: Změňte cestu instalace řešení Office](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
 **Požadavky**  
 Požadavky můžete součástí instalačního programu nebo na požádání stáhnout během instalace.  
  
-   **Stažení požadované součásti z webu dodavatele součásti**: tuto možnost použijte, chcete-li stáhnout všechny tyto požadavky od společnosti Microsoft.  
  
-   **Stáhnout požadavky ze stejného umístění jako Moje aplikace**: tuto možnost použijte k balíčku požadavky do instalační služby. Včetně požadovaných souborů s instalačním programem zvětšuje velikost řešení.  
  
-   **Stažení požadované součásti z následujícího umístění**: tuto možnost použijte, aby požadavky dostupné pro koncové uživatele samostatně jako jiné instalačního programu na webové stránce nebo sdílené síťové složce.  
  
 **Aktualizace**  
 Interval aktualizace Určuje, jak často řešení zkontroluje aktualizace. Ve výchozím nastavení se zkontrolujte každých sedm dní.  
  
 Kontrola aktualizací pokaždé, když je načten přizpůsobení na úrovni dokumentu nebo doplňku VSTO ponechá ji aktualizovat, ale bude mít vliv na výkon při spuštění.  
  
 Pokud nasazujete pomocí disku CD-ROM nebo vyměnitelné jednotky, tuto možnost nastavíte na **nikdy kontrola aktualizací**.  
  
 **Možnosti (popis)**  
 Můžete nastavit možnosti publikování pro následující vlastnosti:  
  
-   Jazyka publikování: národní prostředí řešení Office.  
  
-   Název vydavatele: název společnosti nebo vývojáře, jak se zobrazuje v **přidat nebo odebrat programy** nebo **programy a funkce**.  
  
-   Název produktu: název řešení Office tak, jak se zobrazuje v **přidat nebo odebrat programy** nebo **programy a funkce**.  
  
-   Adresa URL podpory: umístění pro koncové uživatele kontaktovat technickou podporu pro řešení Office.  
  
 **Možnosti (Office nastavení)**  
 Můžete nastavit možnosti publikování pro následující vlastnosti:  
  
-   Název řešení: název řešení Office tak, jak se zobrazí v aplikaci Office.  
  
-   Popis: popis řešení Office tak, jak se zobrazí v aplikaci Office.  
  
-   Chování zatížení doplňku VSTO.  
  
    -   Při spuštění: Určuje, že doplňku VSTO načte při spuštění aplikace Office.  
  
    -   Zatížení na vyžádání: Určuje, že doplňku VSTO načte, když aplikace vyžaduje, například když uživatel klikne na element uživatelského rozhraní, který používá funkce v doplňku VSTO.  
  
 **Jazyka publikování**  
 Tato možnost nastavuje jazyk licenční podmínky pro Software společnosti Microsoft a obsahuje jazykové sady v seznamu požadavků. Jazyk vlastního nastavení nemá vliv. Jazyk v instalační program je určen podle nainstalované jazyky sady Visual Studio.  
  
 Další informace o tom, jak změnit **jazyka publikování**, najdete v části [postupy: Změna jazyka publikování pro aplikaci ClickOnce](/visualstudio/deployment/how-to-change-the-publish-language-for-a-clickonce-application).  
  
 **Verze publikování**  
 Nastaví číslo verze pro přizpůsobení. Při změně číslo verze aplikace publikována jako aktualizace. Do nové složky se vytvoří pro každou verzi během procesu sestavení, abyste zabránili přepsání dříve publikovanou verzi. Jednotlivých součástí verzi publikování (**hlavní**, **menší**, **sestavení**, **revize**) může obsahovat až pět číslic.  
  
 **Zvýšit automaticky revizi při každém vydání**  
 Volitelné. Při výběru (výchozí), **revize** součástí číslo verze se zvýší o jeden pokaždé, když je publikována přizpůsobení. To způsobí, že přizpůsobení, která má být publikován jako aktualizace.  
  
 **Nyní publikování**  
 Publikuje aplikace pomocí aktuální nastavení. Ekvivalentní **Dokončit** v tlačítko **Průvodci publikováním**.  
  
## <a name="see-also"></a>Viz také  
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Požadavky na řešení Office nasazení](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)  
  
  