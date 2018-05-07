---
title: 'Návod: Vytvoření vlastního zaváděcího nástroje s výzvou o ochraně osobních údajů | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- dependencies [.NET Framework], custom bootstrapper package
- deploying applications [Visual Studio], custom prerequisites
- Windows Installer deployment, prerequisites
- prerequisites [.NET Framework], custom bootstrapper package
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 73694df5b6e9e5d4c8b4ad40f16cf60998e9fc82
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-create-a-custom-bootstrapper-with-a-privacy-prompt"></a>Návod: Vytvoření vlastního zaváděcího nástroje s výzvou o ochraně osobních údajů
Můžete nakonfigurovat aplikace ClickOnce k automatické aktualizaci kdy sestavení pomocí novější verze souboru a verze sestavení k dispozici. Abyste měli jistotu, že vaši zákazníci souhlasí s tímto postupem, můžete zobrazit na osobní údaje k nim. Potom budou zvolit, zda chcete udělit oprávnění k aplikaci aktualizovat automaticky. Pokud aplikace není povoleno automatické aktualizace, není potřeba instalovat.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Visual Studio 2010.  
  
## <a name="create-an-update-consent-dialog-box"></a>Aktualizaci souhlasu dialogové okno vytvořit  
 Pokud chcete zobrazit na osobní údaje, vytvořte aplikaci, která se čtenáře dotáže na souhlas s automatickými aktualizacemi pro aplikaci.  
  
#### <a name="to-create-a-consent-dialog-box"></a>Chcete-li vytvořit dialogové okno souhlasu  
  
1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, klikněte na tlačítko **Windows**a potom klikněte na **WindowsFormsApplication**.  
  
3.  Pro **název**, typ **ConsentDialog**a potom klikněte na **OK**.  
  
4.  V Návrháři klepněte na formulář.  
  
5.  V **vlastnosti** změňte **Text** vlastnost **dialogové okno souhlasu aktualizace**.  
  
6.  V **sada nástrojů**, rozbalte položku **všechny formuláře Windows**a přetáhněte ji **popisek** ovládacího prvku do formuláře.  
  
7.  V Návrháři klikněte na ovládací prvek popisek.  
  
8.  V **vlastnosti** změňte **Text** vlastnost pod **vzhled** pro následující:  
  
     Aplikace, která se chystáte instalovat zkontroluje nejnovější aktualizace na webu. Kliknutím na "Souhlasím", umožníte aplikaci kontrolovat a instalovat aktualizace automaticky z Internetu.  
  
9. V **sada nástrojů**, přetáhněte **políčko** řízení středu tvaru.  
  
10. V **vlastnosti** změňte **Text** vlastnost pod **rozložení** k **souhlasím**.  
  
11. V **sada nástrojů**, přetáhněte ji **tlačítko** řízení nižší nalevo od formuláře.  
  
12. V **vlastnosti** změňte **Text** vlastnost pod **rozložení** k **pokračovat**.  
  
13. V **vlastnosti** změňte **(název)** vlastnost pod **návrhu** k **ProceedButton**.  
  
14. V **sada nástrojů**, přetáhněte ji **tlačítko** řízení pravé dolní části formuláře.  
  
15. V **vlastnosti** změňte **Text** vlastnost pod **rozložení** k **zrušit**.  
  
16. V **vlastnosti** změňte **(název)** vlastnost pod **návrhu** k **CancelButton**.  
  
17. V návrháři, dvakrát klikněte **souhlasím** políčko pro vygenerování CheckedChanged obslužné rutiny.  
  
18. V souboru Form1 přidejte následující kód pro CheckedChanged obslužné rutiny.  
  
     [!code-csharp[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]  
  
19. Aktualizovat konstruktoru třídy zakázat **pokračovat** tlačítko ve výchozím nastavení.  
  
     [!code-csharp[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]  
  
20. V souboru Form1 přidejte následující kód pro logickou proměnnou ke sledování, pokud koncový uživatel souhlasí s aktualizacemi online.  
  
     [!code-csharp[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]  
  
21. V návrháři, dvakrát klikněte **pokračovat** pro vygenerování obslužnou rutinu události kliknutí.  
  
22. V souboru Form1, přidejte následující kód pro obslužnou rutinu události kliknutí **pokračovat** tlačítko.  
  
     [!code-csharp[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]  
  
23. V návrháři, dvakrát klikněte **zrušit** pro vygenerování obslužnou rutinu události kliknutí.  
  
24. V souboru Form1, přidejte následující kód pro obslužnou rutinu události kliknutí pro **zrušit** tlačítko.  
  
     [!code-csharp[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]  
  
25. Aktualizujte aplikaci vrátí chybu, pokud koncový uživatel nesouhlasí s aktualizacemi online.  
  
     Visual Basic pouze pro vývojáře:  
  
    1.  V **Průzkumníku řešení**, klikněte na tlačítko **ConsentDialog**.  
  
    2.  Na **projektu** nabídky, klikněte na tlačítko **přidat modul**a potom klikněte na **přidat**.  
  
    3.  V souboru Module1.vb přidejte následující kód.  
  
         [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]  
  
    4.  Na **projektu** nabídky, klikněte na tlačítko **Vlastnosti ConsentDialog**a pak klikněte na tlačítko **aplikace** kartě.  
  
    5.  Zrušte zaškrtnutí políčka **Povolit aplikační rozhraní**.  
  
    6.  V **spouštěcí objekt** rozevírací nabídky vyberte **modul 1**.  
  
        > [!NOTE]
        >  Zakázání rozhraní zakáže funkce, jako je Windows XP vizuální styly, události aplikace, úvodní obrazovka, jedna instance aplikace a další. Další informace najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
     Visual C# pouze pro vývojáře:  
  
     Otevřete soubor Program.cs a přidejte následující kód.  
  
     [!code-csharp[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]  
  
26. Na **sestavení** nabídky, klikněte na tlačítko **BuildSolution**.  
  
## <a name="create-the-custom-bootstrapper-package"></a>Vytvořte zákaznický balíček zaváděcího nástroje  
 Pokud chcete zobrazit řádku ochrany osobních údajů pro koncové uživatele, můžete vytvořit zákaznický balíček zaváděcího nástroje pro dialogové okno souhlasu aktualizace aplikace a její zahrnutí předpokladem je ve všech aplikacích ClickOnce.  
  
 Tento postup ukazuje, jak vytvořit zákaznický balíček zaváděcího nástroje vytvořením v následujících dokumentech:  
  
-   Soubor k popisu obsahu zavaděč manifestu product.xml.  
  
-   Soubor manifestu package.xml seznam lokalizace specifické aspekty vašeho balíčku, například řetězce a licenční podmínky pro software.  
  
-   Dokument pro licenční podmínky pro software.  
  
#### <a name="step-1-to-create-the-bootstrapper-directory"></a>Krok 1: Vytvoření adresáře zaváděcího nástroje  
  
1.  Vytvořte adresář s názvem **UpdateConsentDialog** v %PROGRAMFILES%\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages.  
  
    > [!NOTE]
    >  Může být nutné oprávnění správce k vytvoření této složky.  
  
2.  V adresáři UpdateConsentDialog vytvořte podadresář s názvem cs.  
  
    > [!NOTE]
    >  Vytvořte nový adresář pro každé národní prostředí. Můžete například přidat podadresáře pro národní prostředí fr a de. Tyto adresáře by obsahovat řetězců francouzštinu a češtinu a jazykových sad v případě potřeby.  
  
#### <a name="step-2-to-create-the-productxml-manifest-file"></a>Krok 2: Vytvoření souboru manifestu product.xml  
  
1.  Vytvořte textový soubor s názvem `product.xml`.  
  
2.  V souboru product.xml přidejte následující kód XML. Ujistěte se, že nedojde k přepsání existujícího kódu XML.  
  
    ```  
    <Product  
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      ProductCode="Microsoft.Sample.EULA">  
      <!-- Defines the list of files to be copied on build. -->  
      <PackageFiles CopyAllPackageFiles="false">  
        <PackageFile Name="ConsentDialog.exe"/>  
      </PackageFiles>  
  
      <!-- Defines how to run the Setup package.-->  
      <Commands >  
        <Command PackageFile = "ConsentDialog.exe" Arguments=''>  
          <ExitCodes>  
            <ExitCode Value="0" Result="Success" />  
            <ExitCode Value="-1" Result="Fail" String="AU_Unaccepted" />  
            <DefaultExitCode Result="Fail"   
              FormatMessageFromSystem="true" String="GeneralFailure" />  
          </ExitCodes>  
        </Command>  
      </Commands>  
  
    </Product>  
    ```  
  
3.  Uložte soubor do zaváděcího nástroje UpdateConsentDialog.  
  
#### <a name="step-3-to-create-the-packagexml-manifest-file-and-the-software-license-terms"></a>Krok 3: Vytvoření manifestu package.xml souboru a softwaru licenční podmínky  
  
1.  Vytvořte textový soubor s názvem `package.xml`.  
  
2.  V souboru package.xml přidejte následující kód XML definovat národní prostředí a zahrnují licenční podmínky pro software. Ujistěte se, že nedojde k přepsání existujícího kódu XML.  
  
    ```  
    <Package   
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      Name="DisplayName"  
      Culture="Culture"  
      LicenseAgreement="eula.rtf">  
      <PackageFiles>  
        <PackageFile Name="eula.rtf"/>  
      </PackageFiles>  
  
      <!-- Defines a localizable string table for error messages. -->  
      <Strings>  
        <String Name="DisplayName">Update Consent Dialog</String>  
        <String Name="Culture">en</String>  
        <String Name="AU_Unaccepted">The automatic update agreement is not accepted.</String>  
        <String Name="GeneralFailure">A failure occurred attempting to launch the setup.</String>  
      </Strings>  
    </Package>  
    ```  
  
3.  Uložte soubor do en adresáře v adresáři UpdateConsentDialog zaváděcího nástroje.  
  
4.  Vytvořte dokument s názvem eula.rtf pro licenční podmínky pro software.  
  
    > [!NOTE]
    >  Licenční podmínky pro software by měla obsahovat informace o licencování, záruky, závazky a místními zákony. Tyto soubory by měl být specifické pro národní prostředí, proto se ujistěte, že soubor je uložen ve formátu, který podporuje znaky znakové sady MBCS nebo UNICODE. Informace o obsahu, licenční podmínky pro software vaše právní oddělení.  
  
5.  Uložte dokument do en adresáře v adresáři UpdateConsentDialog zaváděcího nástroje.  
  
6.  V případě potřeby vytvořte nový soubor manifestu package.xml a nový dokument eula.rtf pro licenční podmínky pro každé národní prostředí. Například pokud jste vytvořili pro národní prostředí fr a de, vytvořte samostatné soubory manifestu package.xml a licenční podmínky pro software a uložit je do podadresáře fr a de.  
  
## <a name="set-the-update-consent-application-as-a-prerequisite"></a>Nastavení aplikace aktualizace souhlas s  
 V sadě Visual Studio můžete nastavit aplikaci souhlas aktualizace předpokladem je.  
  
#### <a name="to-set-the-update-consent-application-as-a-prerequisite"></a>K nastavení aplikace aktualizace souhlas s  
  
1.  V **Průzkumníku**, klikněte na název aplikace, který chcete nasadit.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko *ProjectName* **vlastnosti**.  
  
3.  Klikněte **publikovat** a pak klikněte na tlačítko **požadavky**.  
  
4.  Vyberte **dialogové okno aktualizace**.  
  
    > [!NOTE]
    >  Budete muset zavřete a znovu otevřete Visual Studio zobrazíte dialogové okno aktualizace souhlasu v dialogovém okně požadavky.  
  
5.  Click **OK**.  
  
## <a name="create-and-test-the-setup-program"></a>Vytvoření a otestování instalační program  
 Po nastavení aplikace souhlasu aktualizace předpokladem je, můžete vygenerovat instalační program a zaváděcího nástroje pro vaši aplikaci.  
  
#### <a name="to-create-and-test-the-setup-program-by-not-clicking-i-agree"></a>Pro vytvoření a otestování instalační program není kliknutím souhlasím  
  
1.  V **Průzkumníku**, klikněte na název aplikace, který chcete nasadit.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko *ProjectName* **vlastnosti**.  
  
3.  Klikněte **publikovat** a pak klikněte na tlačítko **publikovat**.  
  
4.  Pokud výstup publikování automaticky neotevře, přejděte k publikování výstupu.  
  
5.  Spusťte Setup.exe program.  
  
     Instalační program zobrazí licenční smlouva pro dialogové okno souhlasu aktualizace softwaru.  
  
6.  Přečtěte si licenční smlouvě na software a potom klikněte na **přijmout**.  
  
     Zobrazí se dialogové okno souhlasu aktualizaci aplikace a následující text: aplikace, která se chystáte instalovat zkontroluje nejnovější aktualizace na webu. Kliknutím na souhlasím, umožníte aplikaci vyhledat aktualizace automaticky na Internetu.  
  
7.  Zavře se aplikace nebo klikněte na tlačítko Storno.  
  
     Aplikace zobrazí chyba: došlo k chybě při instalaci komponenty system pro *ApplicationName*. Instalační program nemůže pokračovat, dokud všechny součásti systému byly úspěšně nainstalovány.  
  
8.  Klikněte na tlačítko Podrobnosti, zobrazí se následující chybová zpráva: součást aktualizujte dialogové okno souhlasu se nezdařila instalace se následující chybová zpráva: "Automatické aktualizace nejsou povoleny." Následující součásti se nepodařilo nainstalovat: – dialogové okno souhlasu aktualizace  
  
9. Klikněte na tlačítko **Zavřít**.  
  
#### <a name="to-create-and-test-the-setup-program-by-clicking-i-agree"></a>Pro vytvoření a otestování instalační program klepnutím na tlačítko souhlasím  
  
1.  V **Průzkumníku**, klikněte na název aplikace, který chcete nasadit.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko *ProjectName* **vlastnosti**.  
  
3.  Klikněte **publikovat** a pak klikněte na tlačítko **publikovat**.  
  
4.  Pokud výstup publikování automaticky neotevře, přejděte k publikování výstupu.  
  
5.  Spusťte Setup.exe program.  
  
     Instalační program zobrazí licenční smlouva pro dialogové okno souhlasu aktualizace softwaru.  
  
6.  Přečtěte si licenční smlouvě na software a potom klikněte na **přijmout**.  
  
     Zobrazí se dialogové okno souhlasu aktualizaci aplikace a následující text: aplikace, která se chystáte instalovat zkontroluje nejnovější aktualizace na webu. Kliknutím na souhlasím, umožníte aplikaci vyhledat aktualizace automaticky na Internetu.  
  
7.  Klikněte na tlačítko **souhlasím**a potom klikněte na **pokračovat**.  
  
     Chcete-li nainstalovat spuštěním aplikace.  
  
8.  Pokud se zobrazí dialogové okno instalace, klikněte na tlačítko **nainstalovat**.  
  
## <a name="see-also"></a>Viz také  
 [Požadavky na nasazení aplikací](../deployment/application-deployment-prerequisites.md)   
 [Vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md)   
 [Postupy: vytvoření manifestu produktu](../deployment/how-to-create-a-product-manifest.md)   
 [Postupy: vytvoření manifestu balíčku](../deployment/how-to-create-a-package-manifest.md)   
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)