---
title: "Nasazení řešení Office s použitím technologie ClickOnce | Microsoft Docs"
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
helpviewer_keywords:
- Office development in Visual Studio, deploying solutions
- ClickOnce deployment [Office development in Visual Studio], deploying solutions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a989fe2bc88d25ad81238b65bf8ecd775c39bc35
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="deploying-an-office-solution-by-using-clickonce"></a>Nasazení řešení Office s použitím technologie ClickOnce
  Pokud používáte ClickOnce, můžete nasadit řešení pro Office v méně kroků. Když publikujete aktualizace, vaše řešení je automaticky rozpozná a nainstaluje. Technologie ClickOnce ale vyžaduje, aby bylo řešení nainstalováno zvlášť pro každého uživatele počítače. Proto byste měli zvážit použití Instalační služby systému Windows (souboru .msi), pokud vaše řešení bude používat více než jeden uživatel ve stejném počítači.  
  
## <a name="in-this-topic"></a>V tomto tématu  
  
-   [Publikování řešení](#Publish)  
  
-   [Rozhodněte, jak chcete udělit vztah důvěryhodnosti k řešení](#Trust)  
  
-   [Pomoc uživatelům s instalací řešení](#Helping)  
  
-   [Vložit dokument řešení do počítače koncového uživatele (pouze úpravy na úrovni dokumentů)](#Put)  
  
-   [Vložit dokument řešení na serveru se systémem SharePoint (pouze úpravy na úrovni dokumentů)](#SharePoint)  
  
-   [Vytvořit vlastní instalační program](#Custom)  
  
-   [Publikování aktualizace](#Update)  
  
-   [Změna umístění instalace řešení](#Location)  
  
-   [Vrácení řešení starší verze](#Roll)  
  
 Další informace o nasazení řešení Office tak, že vytvoříte soubor Instalační služby systému Windows najdete v tématu [nasazení řešení Office pomocí Instalační služba systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
##  <a name="Publish"></a>Publikování řešení  
 Řešení můžete publikovat pomocí **Průvodci publikováním** nebo **Návrhář projektu**. V tomto postupu budete používat **Návrhář projektu** protože poskytuje kompletní sadu možnosti publikování. V tématu [publikování průvodce &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/publish-wizard-office-development-in-visual-studio.md).  
  
#### <a name="to-publish-the-solution"></a>Publikování řešení  
  
1.  V **Průzkumníku**, vyberte uzel, který má název pro svůj projekt.  
  
2.  Na řádku nabídek zvolte **projektu**, *ProjectName* **vlastnosti**.  
  
3.  V **Návrhář projektu**, vyberte **publikovat** kartu, která na následujícím obrázku.  
  
     ![Na kartě Publikovat v Návrháři projektu](../vsto/media/vsto-publishtab.png "kartě Publikovat v Návrháři projektu")  
  
4.  V **publikování umístění složky (ftp server nebo cesta k souboru)** pole, zadejte cestu ke složce, kam chcete **Návrhář projektu** zkopírovat soubory řešení.  
  
     Můžete zadat některý z následujících typů cest.  
  
    -   Místní cestu (například *C:\FolderName\FolderName*).  
  
    -   Uniform Naming Convention (UNC) cesta ke složce v síti (například  *\\\ServerName\FolderName*).  
  
    -   Relativní cesta (například *PublishFolder\\*, což je složka, ve které je ve výchozím nastavení publikování projektu).  
  
5.  V **adresy URL instalace složky** zadejte plně kvalifikovanou cestu k umístění, kde se koncovým uživatelům najít řešení.  
  
     Pokud umístění ještě neznáte, nemusíte nic zadejte do tohoto pole. Ve výchozím nastavení hledá technologie ClickOnce aktualizace ve složce, ze které uživatelé řešení instalují.  
  
6.  Vyberte **požadavky** tlačítko.  
  
7.  V **požadavky** dialogové okno pole, ujistěte se, že **vytvořit instalační program pro instalaci požadovaných součástí** je zaškrtnuté políčko.  
  
8.  V **vyberte, které požadavky pro instalaci** seznamu, zaškrtněte políčka pro **Instalační služby systému Windows verze 4.5** a odpovídající balíček rozhraní .NET Framework.  
  
     Například pokud vaše řešení cíle [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], zaškrtněte políčka pro **Instalační služby systému Windows verze 4.5** a **Microsoft .NET Framework 4.5 Full**.  
  
9. Pokud vaše řešení cílem rozhraní .NET Framework 4.5, vyberte také **Visual Studio 2010 Tools for Office Runtime** zaškrtávací políčko.  
  
    > [!NOTE]  
    >  Ve výchozím nastavení toto zaškrtávací políčko se nezobrazuje. Aby se toto zaškrtávací políčko zobrazilo, je nutné vytvořit balíček zaváděcího nástroje. V tématu [vytváření balíčku zaváděcího nástroje pro Office 2013 VSTO doplňku sadou Visual Studio 2012](http://blogs.msdn.com/b/vsto/archive/2012/12/21/creating-a-bootstrapper-package-for-an-office-2013-vsto-add-in-with-visual-studio-2012.aspx).  
  
10. V části **zadejte umístění instalace pro požadavky**, vyberte jednu z možností, které jsou uvedeny a potom zvolte **OK** tlačítko.  
  
     Jednotlivé možnosti jsou popsány v následující tabulce.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |**Stažení požadované součásti z webu dodavatele součásti**|Uživatel bude vyzván, aby od dodavatele stáhl a nainstaloval nezbytné součásti.|  
    |**Stáhnout požadavky ze stejného umístění jako Moje aplikace**|Požadovaný software bude nainstalován spolu s řešením. Pokud zvolíte tuto možnost, sada Visual Studio za vás zkopíruje všechny požadované balíčky do umístění pro publikování. Tato možnost bude fungovat, pouze pokud jsou balíčky požadovaných součástí ve vývojovém počítači.|  
    |**Stažení požadované součásti z následujícího umístění**|Sada Visual Studio zkopíruje všechny balíčky požadovaných součástí do zadaného umístění a nainstaluje je společně s řešením.|  
  
     V tématu [dialogové okno požadavky](/visualstudio/ide/reference/prerequisites-dialog-box).  
  
11. Vyberte **aktualizace** tlačítko, zadejte, jak často chcete koncového uživatele doplňku VSTO nebo vlastní nastavení pro aktualizace a potom zvolte **OK** tlačítko.  
  
    > [!NOTE]  
    >  Pokud nasazujete pomocí disku CD-ROM nebo vyměnitelné jednotky, vyberte **nikdy kontrola aktualizací** tlačítko.  
  
     Informace o tom, jak publikovat aktualizace najdete v tématu [publikování aktualizace](#Update).  
  
12. Vyberte **možnosti** tlačítko, projděte si možnosti v **možnosti** dialogové okno pole a potom vyberte **OK** tlačítko.  
  
13. Vyberte **publikovat** tlačítko.  
  
     Sada Visual Studio přidá následující složky a soubory do složky pro publikování, kterou jste zadali v předchozím kroku tohoto postupu.  
  
    -   **Soubory aplikace** složky.  
  
    -   Instalační program  
  
    -   Manifest nasazení, který odkazuje na manifest nasazení pro nejnovější verzi  
  
     **Soubory aplikace** složka obsahuje podsložky pro každou verzi, která budete publikovat. Jednotlivé podsložky pro konkrétní verzi obsahují následující soubory.  
  
    -   Manifest aplikace  
  
    -   Manifest nasazení  
  
    -   Sestavení přizpůsobení  
  
     Následující obrázek znázorňuje strukturu složky publikovat pro doplňku VSTO v Outlooku.  
  
     ![Struktura složky publikování](../vsto/media/publishfolderstructure.png "publikování struktura složek")  
  
    > [!NOTE]  
    >  ClickOnce příponu .deploy připojí k sestavení tak, aby zabezpečené Instalace Internetové informační služby (IIS) se nebude blokovat soubory z důvodu nebezpečné rozšíření. Až uživatel řešení nainstaluje, technologie ClickOnce příponu .deploy odstraní.  
  
14. Zkopírujte soubory řešení do umístění instalace, které jste zadali v předchozím kroku tohoto postupu.  
  
##  <a name="Trust"></a>Rozhodněte, jak chcete udělit vztah důvěryhodnosti k řešení  
 Aby bylo možné řešení spustit v počítačích uživatelů, musíte buď zajistit jeho důvěryhodnost, nebo uživatelé musejí při instalaci řešení reagovat na výzvu k potvrzení jeho důvěryhodnosti. Pokud chcete zajistit důvěryhodnost řešení, podepište manifesty pomocí certifikátu, který určuje známého a důvěryhodného vydavatele. V tématu [důvěřující řešení pomocí podepisování aplikace a nasazení manifesty](../vsto/granting-trust-to-office-solutions.md#Signing).  
  
 Pokud nasazujete přizpůsobení na úrovni dokumentu a chcete vložit dokument do složky v počítači uživatele nebo zpřístupnit dokument na webu služby SharePoint, ujistěte se, že Office důvěřuje umístění dokumentu. V tématu [udělení důvěry dokumentům](../vsto/granting-trust-to-documents.md).  
  
##  <a name="Helping"></a>Pomoc uživatelům s instalací řešení  
 Uživatelé mohou řešení nainstalovat tak, že spustí instalační program, otevřou manifest nasazení nebo, v případě přizpůsobení na úrovni dokumentu, přímo otevřou dokument. Osvědčeným postupem je instalace řešení pomocí instalačního programu. Tyto dva přístupy nemáte zkontrolujte, zda je nainstalovaný požadovaný software. Pokud uživatelé chtějí otevřít dokument z umístění instalace, musejí jej přidat do seznamu důvěryhodných umístění v Centru zabezpečení aplikace Office.  
  
### <a name="opening-the-document-of-a-document-level-customization"></a>Otevření dokumentu přizpůsobení na úrovni dokumentu  
 Uživatelé mohou otevřít dokument přizpůsobení na úrovni dokumentu přímo z umístění instalace nebo tak, že dokument zkopírují do svého počítače a poté otevřou jeho místní kopii.  
  
 Osvědčeným postupem je, že by uživatelé měli otevřít kopii dokumentu ve svém počítači, aby nemohla nastat situace, kdy se více uživatelů současně pokusí otevřít stejnou kopii. Pro vynucení tohoto postupu můžete nakonfigurovat instalační program tak, aby dokument zkopíroval do počítačů uživatelů. V tématu [do počítače koncového uživatele (pouze přizpůsobení na úrovni dokumentu) umístit dokumentu řešení](#Put).  
  
### <a name="installing-the-solution-by-opening-the-deployment-manifest-from-an-iis-website"></a>Instalace řešení pomocí otevření manifestu nasazení z webu služby IIS  
 Uživatelé mohou nainstalovat řešení pro Office tak, že z webu otevřou manifest nasazení. Zabezpečená instalace Internetové informační služby (IIS) ale bude blokovat soubory s příponou .vsto. Typ MIME musí být definován ve službě IIS před nasazením řešení pro Office pomocí služby IIS.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-60"></a>Přidání typu MIME .vsto do služby IIS 6.0  
  
1.  Na serveru, který běží služby IIS 6.0, zvolte **spustit**, **všechny programy**, **nástroje pro správu**, **Správce Internetové informační služby (IIS)**.  
  
2.  Zvolte název počítače, **weby** složku nebo webový server, který konfigurujete.  
  
3.  Na řádku nabídek zvolte **akce**, **vlastnosti**.  
  
4.  Na **hlavičky protokolu HTTP** , zvolte **typy MIME** tlačítko.  
  
5.  V **typy MIME** okně zvolte **nový** tlačítko.  
  
6.  V **typ MIME** okno, zadejte **.vsto** jako rozšíření, zadejte **application/x-ms-vsto** jako MIME zadejte a potom použijte nové nastavení.  
  
    > [!NOTE]  
    >  Aby se změny projevily, je nutné restartovat službu Publikování na webu nebo počkat na recyklaci pracovního procesu. Následně je nutné vyprázdnit diskovou mezipaměť prohlížeče. Poté zkuste soubor .vsto znovu otevřít.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-70"></a>Chcete-li přidat typ MIME .vsto pro službu IIS 7.0  
  
1.  Na serveru, který běží služby IIS 7.0, zvolte **spustit**, **všechny programy**, **Příslušenství**.  
  
2.  Otevřete místní nabídku pro **příkazového řádku**a potom zvolte **spustit jako správce.**  
  
3.  V **otevřete** pole, zadejte následující cestu a potom zvolte **OK** tlačítko.  
  
    ```  
    %windir%\system32\inetsrv   
    ```  
  
4.  Zadejte následující příkaz a poté použijte nová nastavení.  
  
    ```  
    set config /section:staticContent /+[fileExtension='.vsto',mimeType='application/x-ms-vsto']  
    ```  
  
    > [!NOTE]  
    >  Aby se změny projevily, je nutné restartovat službu Publikování na webu nebo počkat na recyklaci pracovního procesu. Následně je nutné vyprázdnit diskovou mezipaměť prohlížeče. Poté zkuste soubor .vsto znovu otevřít.  
  
##  <a name="Put"></a>Vložit dokument řešení do počítače koncového uživatele (pouze úpravy na úrovni dokumentů)  
 Vytvořením akce po nasazení můžete zkopírovat dokumentu vašeho řešení do počítače koncového uživatele pro ně. Tímto způsobem uživatel nemá k dokumentu ručně zkopírovat z umístění instalace se svými počítači po instalaci vaše řešení. Budete muset vytvořit třídu, která definuje akce po nasazení, sestavení a publikování řešení, upravte manifest aplikace a manifest aplikace a nasazení znovu podepsat.  
  
 Následující postup předpokládá, že je název projektu **ExcelWorkbook** a publikování řešení, aby **C:\publish** adresář ve vašem počítači.  
  
### <a name="create-a-class-that-defines-the-post-deployment-action"></a>Vytvoření třídy, která definuje akci po nasazení  
  
1.  Na řádku nabídek zvolte **soubor**, **přidat**, **nový projekt**.  
  
2.  V **přidat nový projekt** v dialogovém **nainstalovaných šablonách** podokně, vyberte **Windows** složky.  
  
3.  V **šablony** podokně, vyberte **knihovny tříd** šablony.  
  
4.  V **název** zadejte **FileCopyPDA**a potom zvolte **OK** tlačítko.  
  
5.  V **Průzkumníku řešení**, vyberte **FileCopyPDA** projektu.  
  
6.  Na řádku nabídek zvolte **projektu**, **přidat odkaz na**.  
  
7.  Na **.NET** přidejte odkazy na Microsoft.VisualStudio.Tools.Applications.Runtime a Microsoft.VisualStudio.Tools.Applications.ServerDocument.  
  
8.  Přejmenujte třídy pro `FileCopyPDA`a poté nahraďte obsah souboru kódem. Tento kód provede následující:  
  
    -   Zkopíruje dokument na plochu uživatele.  
  
    -   Změní vlastnost _AssemblyLocation z relativní cesty na plně kvalifikovanou cestu k manifestu nasazení.  
  
    -   Odstraní soubor, pokud uživatel řešení odinstaluje.  
  
     [!code-vb[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/VisualBasic/trin_excelworkbookpda/filecopypda/class1.vb#7)]
     [!code-csharp[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/CSharp/trin_excelworkbookpda/filecopypda/class1.cs#7)]  
  
### <a name="build-and-publish-the-solution"></a>Sestavení a publikování řešení  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **FileCopyPDA** projektu a potom vyberte **sestavení**.  
  
2.  Otevřete místní nabídku pro **ExcelWorkbook** projektu a potom vyberte **sestavení**.  
  
3.  Otevřete místní nabídku pro **ExcelWorkbook** projektu a potom vyberte **přidat odkaz na**.  
  
4.  V **přidat odkaz na** dialogovém okně vyberte **projekty** , zvolte **FileCopyPDA**a potom zvolte **OK** tlačítko.  
  
5.  V **Průzkumníku řešení**, vyberte **ExcelWorkbook** projektu.  
  
6.  V řádku nabídek zvolte **projektu**, **novou složku**.  
  
7.  Zadejte **Data**a potom vyberte klávesu Enter.  
  
8.  V **Průzkumníku řešení**, vyberte **Data** složky.  
  
9. Na řádku nabídek zvolte **projektu**, **přidat existující položku**.  
  
10. V **přidat existující položku** dialogové okno, přejděte do výstupního adresáře pro **ExcelWorkbook** projekt, vyberte **ExcelWorkbook.xlsx** souboru a potom vyberte  **Přidat** tlačítko.  
  
11. V **Průzkumníku řešení** zvolte **ExcelWorkbook.xlsx** souboru.  
  
12. V **vlastnosti** změňte **akce sestavení** vlastnost **obsahu** a **kopírovat do výstupního adresáře** vlastnost  **Kopírovat, pokud je novější**.  
  
     Po dokončení těchto kroků, projekt bude vypadat podobně jako na následujícím obrázku.  
  
     ![Struktura projektu akce nasazení post. ] (../vsto/media/vsto-postdeployment.png "Projektu struktura akce nasazení post.")  
  
13. Publikování **ExcelWorkbook** projektu.  
  
### <a name="modify-the-application-manifest"></a>Úprava manifestu aplikace  
  
1.  Otevřete **c:\publish** adresář pomocí **Průzkumníka souborů**.  
  
2.  Otevřete **soubory aplikace** složku a potom otevřete složku, která odpovídá nejnovější publikovaná verze vašeho řešení.  
  
3.  Otevřete **ExcelWorkbook.dll.manifest** soubor v textovém editoru, například Poznámkový blok.  
  
4.  Po `</vstav3:update>` elementu, přidejte následující kód. Pro atribut třídy `<vstav3:entryPoint>` elementu, použijte následující syntaxi: *NamespaceName.ClassName*. V následujícím příkladu, názvy oboru názvů a třídy jsou stejné, takže je výsledný název vstupního bodu `FileCopyPDA.FileCopyPDA`.  
  
    ```  
    <vstav3:postActions>  
      <vstav3:postAction>  
        <vstav3:entryPoint  
          class="FileCopyPDA.FileCopyPDA">  
          <assemblyIdentity  
            name="FileCopyPDA"  
            version="1.0.0.0"  
            language="neutral"  
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:postActionData>  
        </vstav3:postActionData>  
      </vstav3:postAction>  
    </vstav3:postActions>  
    ```  
  
### <a name="re-sign-the-application-and-deployment-manifests"></a>Opětovné podepsání aplikace a manifestů nasazení  
  
1.  V **%USERPROFILE%\Documents\Visual Studio 2013\Projects\ExcelWorkbook\ExcelWorkbook** složce, kopie **ExcelWorkbook_TemporaryKey.pfx** soubor certifikátu a pak ji vložit do  *PublishFolder* **\Application Files\ExcelWorkbook**\__MostRecentPublishedVersion_ složky.
  
2.  Otevřete příkazový řádek sady Visual Studio a pak přejděte do adresáře **c:\publish\Application Files\ExcelWorkbook**\__MostRecentPublishedVersion_ složky (například **c:\publish\Application Files\ExcelWorkbook_1_0_0_4**).  
  
3.  Podepište upravený manifest aplikace spuštěním následujícího příkazu:  
  
    ```  
    mage -sign ExcelWorkbook.dll.manifest -certfile ExcelWorkbook_TemporaryKey.pfx  
    ```  
  
     Zobrazí se zpráva „ExcelWorkbook.dll.manifest successfully signed“ („Soubor ExcelWorkbook.dll.manifest byl úspěšně podepsán.“).  
  
4.  Změnit na **c:\publish** složku a pak aktualizaci a přihlašovací nasazení manifest spuštěním následujícího příkazu:  
  
    ```  
    mage -update ExcelWorkbook.vsto -appmanifest "Application Files\Ex  
    celWorkbookMostRecentVersionNumber>\ExcelWorkbook.dll.manifest" -certfile "Application Files\ExcelWorkbookMostRecentVersionNumber>\ExcelWorkbook_TemporaryKey.pfx"  
    ```  
  
    > [!NOTE]  
    >  V předchozím příkladu nahraďte MostRecentVersionNumber číslo verze naposledy publikovanou verzi vašeho řešení (například **1_0_0_4**).  
  
     Zobrazí se zpráva „ExcelWorkbook.vsto successfully signed“ („Soubor ExcelWorkbook.vsto byl úspěšně podepsán.“).  
  
5.  Zkopírujte soubor ExcelWorkbook.vsto **c:\publish\Application Files\ExcelWorkbook**\__MostRecentVersionNumber_ adresáře.  
  
##  <a name="SharePoint"></a>Vložit dokument řešení na serveru se systémem SharePoint (pouze úpravy na úrovni dokumentů)  
 Přizpůsobení na úrovni dokumentu můžete pro koncové uživatele publikovat pomocí služby SharePoint. Když uživatelé přejdou na web služby SharePoint a dokument otevřou, modul runtime automaticky nainstaluje řešení ze sdílené síťové složky do místního počítače uživatele. Jakmile je řešení nainstalováno místně, bude přizpůsobení nadále fungovat i v případě, že je dokument zkopírován do jiného umístění, například na plochu.  
  
#### <a name="to-put-the-document-on-a-server-thats-running-sharepoint"></a>Umístění dokumentu na server, na kterém je spuštěna služba SharePoint  
  
1.  Přidejte dokument řešení do knihovny dokumentů na webu služby SharePoint.  
  
2.  Proveďte jeden z následujících postupů:  
  
    -   Pomocí konfiguračního nástroje sady Office přidejte server, na němž je spuštěna služba SharePoint, do Centra zabezpečení v aplikaci Word nebo Excel na všech počítačích uživatelů.  
  
         V tématu [zásad zabezpečení a nastavení v Office 2010](http://go.microsoft.com/fwlink/?LinkId=99227).  
  
    -   Postarejte se, aby každý uživatel provedl následující kroky.  
  
        1.  V místním počítači, otevřete Word či Excel, vyberte **soubor** a pak klikněte na příkaz **možnosti** tlačítko.  
  
        2.  V **Centrum zabezpečení** dialogovém okně vyberte **důvěryhodné umístění** tlačítko.  
  
        3.  Vyberte **povolit důvěryhodného umístění v síti (nedoporučuje se)** zaškrtněte políčko a potom vyberte **přidat nové umístění** tlačítko.  
  
        4.  V **cesta** zadejte adresu URL knihovny dokumentů Sharepointu, která obsahuje dokument, který jste nahráli (například *http://SharePointServerName/TeamName/ProjectName/DocumentLibraryName*).  
  
             Název výchozí webové stránky, jako je například default.aspx nebo AllItems.aspx nepřidáte.  
  
        5.  Vyberte **podsložky toto umístění jsou také důvěryhodné** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
             Když uživatelé otevřou dokument z webu služby SharePoint, dokument se otevře a nainstaluje se přizpůsobení. Uživatelé mohou dokument zkopírovat na svou plochu. Přizpůsobení bude stále možné spustit, protože vlastnosti v dokumentu odkazují na síťové umístění dokumentu.  
  
##  <a name="Custom"></a>Vytvořit vlastní instalační program  
 Můžete vytvořit vlastní instalační program pro řešení Office, místo použití instalačního programu, který je pro vás vytvořen při publikování řešení. Můžete například spustit instalaci pomocí přihlašovacího skriptu nebo můžete řešení nainstalovat pomocí dávkového souboru bez zásahu uživatele. Tyto scénáře fungují nejlépe, pokud jsou požadované součásti již nainstalovány v počítačích koncových uživatelů.  
  
 Jako součást procesu vlastní instalace volejte instalační nástroj pro řešení pro Office (VSTOInstaller.exe), který je ve výchozím nastavení nainstalován v následujícím umístění:  
  
 %commonprogramfiles%\microsoft shared\VSTO\10.0\VSTOInstaller.exe  
  
 Pokud se v tomto umístění nenachází, můžete cestu k tomuto nástroji vyhledat pomocí klíče registru HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSTO Runtime Setup\v4\InstallerPath or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSTO Runtime Setup\v4\InstallerPath.  
  
 Nástroj VSTOinstaller.exe podporuje následující parametry.  
  
|Parametr|Definice|  
|---------------|----------------|  
|/Install nebo /I|Nainstaluje řešení. Za tímto parametrem musí následovat cesta k manifestu nasazení. Můžete zadat cestu v místním počítači, universal naming convention (UNC) sdílené složky. Můžete zadat místní cestu (*C:\FolderName\PublishFolder*), je relativní cesta (*publikovat\\*), nebo plně kvalifikovaný umístění (*\\\ServerName\ Název složky* nebo http://*ServerName/název_složky*).|  
|/Uninstall nebo /U|Odinstaluje řešení. Za tímto parametrem musí následovat cesta k manifestu nasazení. Můžete zadat že cestu k může být v místním počítači, sdílené složky UNC. Můžete zadat místní cestu (*c:\FolderName\PublishFolder*), je relativní cesta (*publikovat\\*), nebo plně kvalifikovaný umístění (*\\\ServerName\ Název složky* nebo http://*ServerName/název_složky*).|  
|/Silent nebo /S|Při instalaci nebo odinstalaci se uživatelům nebudou zobrazovat výzvy k zadání vstupu ani žádné jiné zprávy. Pokud se požaduje výzvu vztahu důvěryhodnosti, přizpůsobení není nainstalovaná nebo aktualizovat.|  
|/Help nebo /?|Zobrazí informace nápovědy.|  
  
 Po spuštění nástroje VSTOinstaller.exe se mohou zobrazit následující kódy chyb.  
  
|Kód chyby|Definice|  
|----------------|----------------|  
|0|Řešení bylo úspěšně nainstalováno či odinstalováno nebo se zobrazila nápověda nástroje VSTOInstaller.|  
|-100|Jeden nebo více parametrů příkazového řádku není platných nebo byly nastaveny více než jedenkrát. Další informace, zadejte "Instalační službě VSTO /?" nebo najdete [vytváření vlastní instalační program pro řešení Office ClickOnce](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e).|  
|-101|Jeden nebo více možností příkazového řádku jsou neplatné. Pokud chcete získat další informace, zadejte příkaz "vstoinstaller /?".|  
|-200|Manifest nasazení identifikátor URI není platný. Pokud chcete získat další informace, zadejte příkaz "vstoinstaller /?".|  
|-201|Řešení nelze nainstalovat, protože manifest nasazení není platná. V tématu [manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md).|  
|-202|Řešení nelze nainstalovat, protože Visual Studio Tools for Office oddílu manifest aplikace není platný. V tématu [manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md).|  
|-203|Řešení nelze nainstalovat, protože došlo k chybě stahování. Zkontrolujte identifikátor URI nebo síťové umístění souboru manifestu nasazení a akci opakujte.|  
|-300|Řešení nelze nainstalovat, protože došlo k výjimce zabezpečení. V tématu [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).|  
|-400|Nelze nainstalovat, řešení.|  
|-401|Nelze odinstalovat, řešení.|  
|-500|Operace byla zrušena, protože řešení nelze nainstalovat nebo odinstalovat nebo nelze stáhnout manifest nasazení.|  
  
##  <a name="Update"></a>Publikování aktualizace  
 Pokud chcete aktualizovat řešení, je publikovat ho znovu pomocí **Návrhář projektu** nebo **Průvodci publikováním**, a poté zkopírujte aktualizované řešení do umístění instalace. Při kopírování souborů do umístění instalace je nutné přepsat předchozí soubory.  
  
 Při příštím spuštění ověří řešení pro aktualizaci, ho budete najít a načíst nové verze automaticky.  
  
##  <a name="Location"></a>Změna umístění instalace řešení  
 Po publikování řešení můžete přidat nebo změnit cestu instalace. Změnit cestu instalace může být vhodné z některého z následujících důvodů:  
  
-   Instalační program byl zkompilován ještě předtím, než byla známa cesta instalace.  
  
-   Soubory řešení byly zkopírovány do jiného umístění.  
  
-   Změnil se název nebo umístění serveru, který hostuje instalační soubory.  
  
 Pokud chcete pro řešení změnit cestu instalace, je nutné aktualizovat instalační program, který poté uživatelé musejí spustit. V případě přizpůsobení na úrovni dokumentu musejí uživatelé také aktualizovat vlastnost v dokumentu tak, aby odkazovala na nové umístění.  
  
> [!NOTE]  
>  Pokud nechcete uživatele požádejte, aby aktualizaci jejich vlastností dokumentu, můžete požádat uživatele k získání aktualizovaného dokumentu z umístění instalace.  
  
#### <a name="to-change-the-installation-path-in-the-setup-program"></a>Změna cesty instalace v instalačním programu  
  
1.  Otevřete **příkazového řádku** okno a potom změnit adresáře pro instalační složku.  
  
2.  Spusťte instalační program a zahrnout `/url` parametr, který přebírá novou instalační cestu jako řetězec.  
  
     Následující příklad ukazuje, jak změnit cestu instalace na umístění na webu společnosti Fabrikam. Tuto adresu URL můžete nahradit požadovanou cestou:  
  
    ```  
    setup.exe /url="http://www.fabrikam.com/newlocation"  
    ```  
  
    > [!NOTE]  
    >  Pokud se zobrazí zpráva, že bude zrušena platnost podpisu spustitelného souboru, znamená to, že certifikát, pomocí něhož bylo řešení podepsáno, již není platný a vydavatel je neznámý. V důsledku toho budou uživatelé muset před instalací řešení potvrdit, že zdroj řešení považují za důvěryhodný.  
  
    > [!NOTE]  
    >  Chcete-li zobrazit aktuální hodnotu adresy URL, spusťte `setup.exe /url`.  
  
 Pro úpravy na úrovni dokumentů musí uživatelé otevřít dokument a aktualizujte jeho _AssemblyLocation – vlastnost. To mohou uživatelé provést pomocí následujícího postupu.  
  
#### <a name="to-update-the-assemblylocation-property-in-a-document"></a>Aktualizace vlastnosti _AssemblyLocation v dokumentu  
  
1.  Na **soubor** , zvolte **informace**, který znázorňuje následující obrázek.  
  
     ![Informace o kartě v aplikaci Excel](../vsto/media/vsto-infotab.png "informace o kartě v aplikaci Excel")  
  
2.  V **vlastnosti** vyberte **Upřesnit vlastnosti**, který znázorňuje následující obrázek.  
  
     ![Rozšířené vlastnosti v aplikaci Excel. ] (../vsto/media/vsto-advanceddocumentproperties.png "Rozšířené vlastnosti v aplikaci Excel.")  
  
3.  Na **vlastní** ve **vlastnosti** vyberte _AssemblyLocation, jak ukazuje následující obrázek.  
  
     ![Vlastnost AssemblyLocation. ] (../vsto/media/vsto-assemblylocationproperty.png "AssemblyLocation vlastnost.")  
  
     **Hodnotu** pole obsahuje identifikátor manifestu nasazení.  
  
4.  Před identifikátor, zadejte plně kvalifikovanou cestu k dokumentu, za nímž následuje panelu, ve formátu *cesta*|*identifikátor* (například *File://ServerName/ Název složky/FileName | 74744e4b-e4d6-41eb-84f7-ad20346fe2d9*.  
  
     Další informace o tom, jak tento identifikátor formátu najdete v tématu [přehled vlastností dokumentu vlastní](../vsto/custom-document-properties-overview.md).  
  
5.  Vyberte **OK** tlačítko a potom uložte a zavřete dokument.  
  
6.  Nainstalujte řešení do zadaného umístění tak, že spustíte instalační program bez parametru /url.  
  
##  <a name="Roll"></a>Vrácení řešení starší verze  
 Když vrátíte řešení zpět, budou uživatelé opět používat předchozí verzi tohoto řešení.  
  
#### <a name="to-roll-back-a-solution"></a>Vrácení řešení zpět  
  
1.  Otevřete umístění instalace řešení.  
  
2.  Na nejvyšší úrovni struktury složky pro publikování odstraňte manifest nasazení (soubor .vsto).  
  
3.  Vyhledejte podsložku pro verzi, kterou chcete vrátit zpět.  
  
4.  Zkopírujte manifest nasazení z této podsložky do složky na nejvyšší úrovni.  
  
     Například pro vrácení řešení, která je volána **OutlookAddIn1** z verze 1.0.0.1 na verzi 1.0.0.0, zkopírujte soubor **OutlookAddIn1.vsto** z **OutlookAddIn1_1_0_0_0** složky. Vložení souborů do nejvyšší úrovně publikování složky, přepsal manifest nasazení specifické pro verzi pro **OutlookAddIn1_1_0_0_1** , který byl již existuje.  
  
     Následující ilustrace znázorňuje strukturu složky pro publikování v tomto příkladu.  
  
     ![Struktura složky publikování](../vsto/media/publishfolderstructure.png "publikování struktura složek")  
  
     Až uživatel příště otevře aplikaci nebo upravený dokument, bude detekována změna manifestu nasazení. Předchozí verze řešení pro Office se spustí z mezipaměti technologie ClickOnce.  
  
> [!NOTE]  
>  Místní data jsou uložena pouze pro jednu předchozí verzi řešení. Pokud je tuto dvě verze, nezachovají se místní data. Další informace o místní data, najdete v části [přístup k místním a vzdáleným datům v aplikacích ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).  
  
## <a name="see-also"></a>Viz také  
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Publikování řešení pro systém Office](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Postupy: publikování řešení Office s použitím technologie ClickOnce](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)   
 [Postupy: Instalace řešení ClickOnce Office](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065)   
 [Postupy: publikování řešení úrovni dokumentu Office SharePoint Server s použitím technologie ClickOnce](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58)   
 [Vytvoření vlastního instalátoru pro řešení ClickOnce Office](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e)  
  
  
