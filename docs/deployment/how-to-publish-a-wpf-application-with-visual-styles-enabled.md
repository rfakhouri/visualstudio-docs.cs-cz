---
title: 'Postupy: publikování aplikace WPF s povolenými vizuálními styly | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
ms.assetid: 73b22b02-fc75-42aa-82d3-51fdcaf8e5c8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 2fbf3c2573d02111f5d1309fb80ceb09aa09f2e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-publish-a-wpf-application-with-visual-styles-enabled"></a>Postupy: Publikování aplikace WPF s povolenými vizuálními styly
Vizuální styly povolit vzhled běžné ovládací prvky, chcete-li změnit podle motiv volená uživatelem. Ve výchozím nastavení nejsou povolené vizuální styly pro aplikace Windows Presentation Foundation (WPF), takže je nutné ručně povolit. Povolení vizuální styly pro aplikaci WPF a poté publikujete řešení způsobí chybu. Toto téma popisuje, jak vyřešit tuto chybu a proces pro publikování aplikace WPF s povolenými vizuálními styly. Další informace o vizuální styly najdete v tématu [vizuální styly přehled](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e). Další informace o chybovou zprávu najdete v tématu [řešení potíží s konkrétní chyby v nasazeních ClickOnce](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md).  
  
 Chcete-li vyřešit chyby a publikování řešení, je třeba provést následující úlohy:  
  
-   [Publikování řešení bez povolenými vizuálními styly](#BKMK_publishsolwovs).  
  
-   [Vytvořte soubor manifestu](#BKMK_CreateManifest).  
  
-   [Vložení souboru manifestu do spustitelného souboru publikované řešení](#BKMK_embedmanifest).  
  
-   [Podepisování manifestů aplikace a nasazení](#BKMK_signappdeplyman).  
  
 Potom můžete přesunout publikované soubory do umístění, ze kterého chcete koncovým uživatelům k instalaci aplikace.  
  
##  <a name="BKMK_publishsolwovs"></a> Publikování řešení bez povolenými vizuálními styly  
  
1.  Ujistěte se, že váš projekt nemá povolenými vizuálními styly. Nejdřív zkontrolujte soubor manifestu vašeho projektu, pro následující kód XML. Poté Pokud se nachází soubor XML, uzavřete XML s značkou komentář.  
  
     Vizuální styly nejsou ve výchozím nastavení povolené.  
  
    ```  
    <dependency>    <dependentAssembly>      <assemblyIdentity          type="win32"          name="Microsoft.Windows.Common-Controls"          version="6.0.0.0"          processorArchitecture="*"          publicKeyToken="6595b64144ccf1df"          language="*"        />    </dependentAssembly>  </dependency>  
    ```  
  
     Následující postupy ukazují, jak otevřít soubor manifestu, které jsou přidružené k projektu.  
  
    ###### <a name="to-open-the-manifest-file-in-a-visual-basic-project"></a>Otevřete soubor manifestu v projektu jazyka Visual Basic  
  
    1.  Na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**, kde *ProjectName* je název projektu WPF.  
  
         Stránky vlastností pro svůj projekt WPF zobrazí.  
  
    2.  Na **aplikace** , zvolte **zobrazení nastavení systému Windows**.  
  
         Otevře se soubor app.manifest v **Editor kódu**.  
  
    ###### <a name="to-open-the-manifest-file-in-a-c-project"></a>Otevřete soubor manifestu v projektu jazyka C#  
  
    1.  Na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**, kde *ProjectName* je název projektu WPF.  
  
         Stránky vlastností pro svůj projekt WPF zobrazí.  
  
    2.  Na **aplikace** kartě, poznamenejte si název, který se zobrazí v poli manifestu. Toto je název manifestu, který je přidružen projektu.  
  
        > [!NOTE]
        >  Pokud **vložení manifestu s výchozím nastavením** nebo **vytvořit aplikaci bez manifestu** objeví v poli manifestu vizuální styly nejsou povoleny. Pokud název souboru manifestu se zobrazí v poli manifestu, pokračujte dalším krokem v tomto postupu.  
  
    3.  V **Průzkumníku řešení**, zvolte **zobrazit všechny soubory** ().  
  
         Toto tlačítko se zobrazí všechny položky projektu, včetně těch, které byly vyloučeny a ty, které jsou obvykle skryta. Soubor manifestu se zobrazí jako položka projektu.  
  
2.  Sestavení a publikování řešení. Další informace o tom, jak publikovat řešení najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
##  <a name="BKMK_CreateManifest"></a> Vytvořte soubor manifestu  
  
1.  Vložte následující kód XML do souboru poznámkového bloku.  
  
     Tato konfigurace XML popisuje sestavení, které obsahuje ovládací prvky, které podporují vizuální styly.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?><asmv1:assembly manifestVersion="1.0"                xmlns="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  <dependency>    <dependentAssembly>      <assemblyIdentity        type="win32"        name="Microsoft.Windows.Common-Controls"        version="6.0.0.0"        processorArchitecture="*"        publicKeyToken="6595b64144ccf1df"        language="*"        />    </dependentAssembly>  </dependency></asmv1:assembly>  
    ```  
  
2.  V poznámkovém bloku klikněte na tlačítko **soubor**a potom klikněte na **uložit jako**.  
  
3.  V **uložit jako** dialogu **uložit jako typ** rozevíracího seznamu vyberte **všechny soubory**.  
  
4.  V **název souboru** zadejte název souboru a připojit **manifest** na konci názvu souboru. Příklad: **themes.manifest**.  
  
5.  Vyberte **procházet složky** tlačítko, vyberte libovolné složky a potom klikněte na **Uložit**.  
  
    > [!NOTE]
    >  Zbývající postupech se předpokládá, že název tohoto souboru je **themes.manifest** a který je uložený soubor do adresáře C:\temp ve vašem počítači.  
  
##  <a name="BKMK_embedmanifest"></a> Vložení souboru manifestu do spustitelného souboru publikované řešení  
  
1.  Otevřete **příkazového řádku Visual Studia**.  
  
     Další informace o tom, jak otevřít **Visual Studio – příkazový řádek**, najdete v části [příkazového řádku](/dotnet/framework/tools/developer-command-prompt-for-vs).  
  
    > [!NOTE]
    >  Příklady zbývajících kroků zkontrolujte následující předpoklady týkající se řešení:  
    >   
    >  -   Název řešení je **MyWPFProject**.  
    > -   Řešení se nachází v následujícím adresáři: `%UserProfile%\Documents\Visual Studio 2010\Projects\`.  
    >   
    >      Řešení je publikována na následující adresář: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish`.  
    > -   Nejnovější verzi souborů publikované aplikace se nachází v následujícím adresáři: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish\Application Files\WPFApp_1_0_0_0`  
    >   
    >  Nemusíte používat název nebo umístění adresáře, které jsou popsané výše. Název a umístění, které jsou popsané výše slouží pouze k objasnění kroky potřebné k publikování vašeho řešení.  
  
2.  Na příkazovém řádku změňte cestu k adresáři, který obsahuje nejnovější verzi souborů publikované aplikace. Následující příklad ukazuje, tento krok.  
  
    ```  
    cd "%UserProfile%\Documents\Visual Studio 2010\Projects\MyWPFProject\publish\Application Files\WPFApp_1_0_0_0"  
    ```  
  
3.  Na příkazovém řádku spusťte následující příkaz pro vložení souboru manifestu do spustitelný soubor aplikace.  
  
    ```  
    mt -manifest c:\temp\themes.manifest -outputresource:MyWPFApp.exe.deploy  
    ```  
  
##  <a name="BKMK_signappdeplyman"></a> Podepisování manifestů aplikace a nasazení  
  
1.  Na příkazovém řádku spusťte následující příkaz pro odebrání `.deploy` rozšíření ze spustitelného souboru v aktuálním adresáři.  
  
    ```  
    ren MyWPFApp.exe.deploy MyWPFApp.exe  
    ```  
  
    > [!NOTE]
    >  Tento příklad předpokládá, že pouze jeden soubor má `.deploy` příponu souboru. Ujistěte se, že přejmenujete všechny soubory v tomto adresáři, které mají `.deploy` příponu souboru.  
  
2.  Na příkazovém řádku spusťte následující příkaz k podepsání manifestu aplikace.  
  
    ```  
    mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  Tento příklad předpokládá podepsání manifestu pomocí `.pfx` souboru projektu. Pokud nejsou podepsání manifestu, můžete vynechat `-cf` parametr, který se používá v tomto příkladu. Pokud se registrujete manifest s certifikátem, který vyžaduje heslo, zadejte `-password` možnost (`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`).  
  
3.  Na příkazovém řádku spusťte následující příkaz pro přidání `.deploy` rozšíření k názvu souboru, který jste přejmenovali v předchozím kroku tohoto postupu.  
  
    ```  
    ren MyWPFApp.exe MyWPFApp.exe.deploy  
    ```  
  
    > [!NOTE]
    >  Tento příklad předpokládá, že pouze jeden soubor měl `.deploy` příponu souboru. Ujistěte se, že přejmenujete všechny soubory v tomto adresáři, ve kterém byla dříve `.deploy` příponou názvu souboru.  
  
4.  Na příkazovém řádku spusťte následující příkaz k podepsání manifestu nasazení.  
  
    ```  
    mage -u ..\..\MyWPFApp.application -appm MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  Tento příklad předpokládá podepsání manifestu pomocí `.pfx` souboru projektu. Pokud nejsou podepsání manifestu, můžete vynechat `-cf` parametr, který se používá v tomto příkladu. Pokud se registrujete manifest s certifikátem, který vyžaduje heslo, zadejte `-password` možnost, jak ukazuje tento příklad:`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`.  
  
 Po provedení těchto kroků můžete přesunout publikované soubory do umístění, ze kterého chcete koncovým uživatelům k instalaci aplikace. Pokud máte v úmyslu často aktualizovat řešení, můžete přesunout tyto příkazy do skriptu a spusťte skript každém publikování nové verze.  
  
## <a name="see-also"></a>Viz také  
 [Řešení konkrétních chyb v nasazeních ClickOnce](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)   
 [Vizuální styly – přehled](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)   
 [Povolení vizuální styly](https://msdn.microsoft.com/library/bb773175.aspx)   
 [Příkazové řádky](/dotnet/framework/tools/developer-command-prompt-for-vs)