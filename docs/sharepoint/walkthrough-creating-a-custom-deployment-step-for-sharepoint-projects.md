---
title: 'Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: aee7c1bf7a7a8d71d02da7bab270c4df1a4a52ab
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120205"
---
# <a name="walkthrough-create-a-custom-deployment-step-for-sharepoint-projects"></a>Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint
  Při nasazení projektu služby SharePoint, Visual Studio provede sérii kroků nasazení v určitém pořadí. Visual Studio zahrnuje mnoho kroků předdefinované nasazení, ale můžete taky vytvořit svoje vlastní.  
  
 V tomto návodu vytvoříte vlastního kroku nasazení pro upgradování řešení na serveru se systémem SharePoint. Sada Visual Studio obsahuje vestavěné kroky nasazení pro celou řadu úloh, tyto se výsuvné nebo přidání řešení, ale neobsahuje kroku nasazení pro upgrade řešení. Ve výchozím nastavení, když nasadíte řešení služby SharePoint, Visual Studio nejprve odvolá řešení (pokud už je nasazený) a poté opětovně nasadí celé řešení. Další informace o postupu předdefinované nasazení najdete v tématu [nasazení, publikování a upgradování balíčků řešení služby SharePoint](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření rozšíření pro Visual Studio, který provádí dvě hlavní úlohy:  
  
    -   Rozšíření definuje vlastního kroku nasazení pro upgradování řešení služby SharePoint.  
  
    -   Rozšíření vytvoří rozšíření projektu, který definuje novou konfiguraci nasazení, který je sada kroky nasazení, které jsou spouštěny pro daný projekt. Novou konfiguraci nasazení obsahuje vlastní nasazení krok a několik kroků předdefinované nasazení.  
  
-   Vytvořte dva vlastní příkazy služby SharePoint, které volá sestavení rozšíření. SharePoint – příkazy jsou metody, které je možné volat v sestavení rozšíření pro použití rozhraní API v objektovém modelu serveru pro službu SharePoint. Další informace najdete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   Vytváření rozšíření pro Visual Studio (VSIX) balíčku pro nasazení obě sestavení.  
  
-   Testování kroku nového nasazení.  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení rozšíření. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Pomocí objektový model serveru pro službu SharePoint. Další informace najdete v tématu [pomocí objektového modelu služby SharePoint Foundation na straně serveru](http://go.microsoft.com/fwlink/?LinkId=177796).  
  
-   Řešení služby SharePoint. Další informace najdete v tématu [přehled řešení](http://go.microsoft.com/fwlink/?LinkId=169422).  
  
-   Upgradování řešení služby SharePoint. Další informace najdete v tématu [upgrade řešení](http://go.microsoft.com/fwlink/?LinkId=177802).  
  
## <a name="create-the-projects"></a>Vytváření projektů
 Pro dokončení tohoto návodu, musíte vytvořit tří projektů:  
  
-   Projekt VSIX k vytvoření balíčku VSIX pro nasazení rozšíření.  
  
-   Projekt knihovny tříd, který implementuje rozšíření. Tento projekt musí mít jako cíl rozhraní .NET Framework 4.5.  
  
-   Projekt knihovny tříd, která definuje vlastní příkazy služby SharePoint. Tento projekt musí mít jako cíl pro rozhraní .NET Framework 3.5.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
4.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
5.  Vyberte **projektu VSIX** šablony, název projektu **UpgradeDeploymentStep**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **UpgradeDeploymentStep** projektu do **Průzkumníku řešení**.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel UpgradeDeploymentStep řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **Windows** uzlu.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
4.  Vyberte **knihovny tříd** projektu šablony, název projektu **DeploymentStepExtension**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **DeploymentStepExtension** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
#### <a name="to-create-the-sharepoint-command-project"></a>Chcete-li vytvořit příkaz projektu služby SharePoint  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel UpgradeDeploymentStep řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **Windows** uzlu.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 3.5** v seznamu verze rozhraní .NET Framework.  
  
4.  Vyberte **knihovny tříd** projektu šablony, název projektu **SharePointCommands**a potom zvolte **OK** tlačítko.  
  
     Visual Studio. přidá **SharePointCommands** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configure-the-projects"></a>Konfigurace projektů
 Než napíšete kód k vytvoření vlastní nasazení krok, je třeba přidat soubory kódu a odkazy na sestavení a je nutné nakonfigurovat projektů.  
  
#### <a name="to-configure-the-deploymentstepextension-project"></a>Ke konfiguraci projektu DeploymentStepExtension
  
1.  V **DeploymentStepExtension** projekt, přidejte dva soubory kódu, které mají tyto názvy:  
  
    -   UpgradeStep  
  
    -   DeploymentConfigurationExtension  
  
2.  Otevřete místní nabídky na DeploymentStepExtension projekt a zvolte **přidat odkaz na**.  
  
3.  Na **Framework** kartě, zaškrtněte políčko pro System.ComponentModel.Composition sestavení.  
  
4.  Na **rozšíření** kartě, zaškrtněte políčko pro sestavení Microsoft.VisualStudio.SharePoint a potom zvolte **OK** tlačítko.  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>Ke konfiguraci projektu SharePointCommands
  
1.  V **SharePointCommands** projekt, přidejte kód souboru, který je pojmenován příkazy.  
  
2.  V **Průzkumníku řešení**, otevřete v místní nabídce **SharePointCommands** uzel projektu a potom zvolte **přidat odkaz na**.  
  
3.  Na **rozšíření** kartě, zaškrtněte políčka pro následující sestavení a potom klikněte na tlačítko zvolte **OK** tlačítko  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
## <a name="define-the-custom-deployment-step"></a>Definování krok vlastní nasazení
 Vytvořte třídu, která definuje krok upgradu nasazení. K definování nasazení krok, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> rozhraní. Toto rozhraní implementujte, kdykoli budete chtít definovat vlastního kroku nasazení.  
  
#### <a name="to-define-the-custom-deployment-step"></a>Chcete-li definovat vlastní nasazení krok  
  
1.  V **DeploymentStepExtension** projektu, otevřete soubor UpgradeStep kód a potom vložte následující kód do ní.  
  
    > [!NOTE]  
    >  Po přidání tohoto kódu, projekt bude mít některé chyby při kompilaci, ale budete ji okamžitě přejděte po přidání kódu v dalších krocích.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/upgradestep.cs#1)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/upgradestep.vb#1)]  
  
## <a name="create-a-deployment-configuration-that-includes-the-custom-deployment-step"></a>Vytvoření konfigurace nasazení, které zahrnuje krok vlastní nasazení
 Vytváření rozšíření projektu pro novou konfiguraci nasazení, která zahrnuje několik kroků předdefinované nasazení a nový krok upgradu nasazení. Vytvořením toto rozšíření vám pomoci vývojářům SharePoint použít krok nasazení upgradu v projektu služby SharePoint.  
  
 Pro vytvoření konfigurace nasazení, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> rozhraní. Toto rozhraní implementujte, kdykoli budete chtít vytváření rozšíření projektu služby SharePoint.  
  
#### <a name="to-create-the-deployment-configuration"></a>Pro vytvoření konfigurace nasazení  
  
1.  V **DeploymentStepExtension** projektu, otevřete soubor DeploymentConfigurationExtension kód a potom vložte následující kód do ní.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/deploymentconfigurationextension.cs#2)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/deploymentconfigurationextension.vb#2)]  
  
## <a name="create-the-custom-sharepoint-commands"></a>Vytvoření vlastních příkazů služby SharePoint
 Vytvořte dva vlastní příkazy, které volají do objektový model serveru pro službu SharePoint. Jeden příkaz určuje, jestli je už nasazená řešení; Další příkaz upgraduje řešení.  
  
#### <a name="to-define-the-sharepoint-commands"></a>Chcete-li definovat příkazy služby SharePoint  
  
1.  V **SharePointCommands** projektu, otevřete soubor kódu příkazy a potom vložte následující kód do ní.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/SharePointCommands/Commands.cs#4)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/sharepointcommands/commands.vb#4)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návodu, jsou všechny kód pro příkazy služby SharePoint a vlastní nasazení krok v projektech. Sestavení je zajistit, že by kompilovat bez chyb.  
  
#### <a name="to-build-the-projects"></a>K sestavení projektů  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **DeploymentStepExtension** projektu a potom vyberte **sestavení**.  
  
2.  Otevřete místní nabídku pro **SharePointCommands** projektu a potom vyberte **sestavení**.  
  
## <a name="create-a-vsix-package-to-deploy-the-extension"></a>Vytvoření balíčku VSIX pro nasazení rozšíření
 K nasazení rozšíření, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest v projektu VSIX. Pak vytvořte balíček VSIX sestavení řešení.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Ke konfiguraci a vytvoření balíčku VSIX  
  
1.  V **Průzkumníku řešení**v části **UpgradeDeploymentStep** projektu, otevřete místní nabídku pro **source.extension.vsixmanifest** souboru a potom vyberte  **Otevřete**.  
  
     Visual Studio otevře soubor v editoru manifestu. Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest, které vyžadují všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **Upgrade kroku nasazení pro projekty SharePoint**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **poskytuje vlastní nasazení upgradu krok, který lze použít v projekty SharePoint**.  
  
5.  V **prostředky** karta editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** vyberte **DeploymentStepExtension**a potom zvolte **OK** tlačítko.  
  
9. V editoru manifestu zvolte **nový** tlačítko znovu.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
10. V **typ** seznamu, zadejte **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  Tento element určuje vlastní rozšíření, které chcete zahrnout do rozšíření sady Visual Studio. Další informace najdete v tématu [Element Asset (VSX schéma)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
11. V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
12. V **projektu** vyberte **SharePointCommands**a potom zvolte **OK** tlačítko.  
  
13. Na řádku nabídek zvolte **sestavení** > **sestavit řešení**a pak se ujistěte, že řešení zkompiluje bez chyb.  
  
14. Ujistěte se, že výstupní složky sestavení projektu UpgradeDeploymentStep nyní obsahuje soubor UpgradeDeploymentStep.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složky pod složkou, která obsahuje soubor projektu.  
  
## <a name="prepare-to-test-the-upgrade-deployment-step"></a>Příprava pro testování v kroku nasazení upgradu
 K testování v kroku upgradu nasazení, je nejprve nutné zavést ukázkové řešení na webu služby SharePoint. Spusťte ladění rozšíření v experimentální instanci sady Visual Studio. Pak vytvořte instanci seznamu použít k testování kroku nasazení a definice seznamu a pak je nasadit na web služby SharePoint. V dalším kroku změnit definice seznamu a instanci seznamu a znovu je ukázka, jak výchozí proces nasazení přepíše řešení na webu služby SharePoint.  
  
 Dále v tomto návodu budete upravovat definice seznamu a instanci seznamu a pak je budete upgradovat na webu služby SharePoint.  
  
#### <a name="to-start-debugging-the-extension"></a>Spustit ladění – rozšíření  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete UpgradeDeploymentStep řešení.  
  
2.  V projektu DeploymentStepExtension otevřete soubor UpgradeStep kódu a pak přidejte zarážku na první řádek kódu `CanExecute` a `Execute` metody.  
  
3.  Spuštění ladění výběrem **F5** klíč, nebo v nabídce panelu Výběr **ladění** > **spustit ladění**.  
  
4.  Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Upgrade kroku nasazení pro Projects\1.0 služby SharePoint a spustí experimentální instanci sady Visual Studio. V kroku nasazení upgradu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-create-a-sharepoint-project-with-a-list-definition-and-a-list-instance"></a>Vytvoření projektu služby SharePoint pomocí definice seznamu a instanci seznamu  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** uzlu nebo **jazyka Visual Basic** uzlu, rozbalte **SharePoint** uzlu a potom vyberte **2010** uzlu.  
  
3.  V horní části dialogových oken, ujistěte se, že **rozhraní .NET Framework 3.5** se zobrazí v seznamu verze rozhraní .NET Framework.  
  
     Projekty pro [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] a [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] vyžadovat tuto verzi rozhraní .NET Framework.  
  
4.  V seznamu šablon projektu, zvolte **projektu služby SharePoint 2010**, název projektu **EmployeesListDefinition**a potom zvolte **OK** tlačítko.  
  
5.  V **Průvodce vlastním nastavením SharePoint**, zadejte adresu URL webu, který chcete použít pro ladění.  
  
6.  V části **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint**, vyberte **nasadit jako řešení farmy** tlačítko.  
  
    > [!NOTE]  
    >  Nasazení upgradu krok nepodporuje řešení v izolovaném prostoru.  
  
7.  Vyberte **Dokončit** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Vytvoří EmployeesListDefinition projekt.  
  
8.  Otevřete místní nabídky projektu EmployeesListDefinition, zvolte **přidat**a potom zvolte **novou položku**.  
  
9. V **přidat novou položku – EmployeesListDefinition** dialogové okno, rozbalte seznam **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
10. Vyberte **seznamu** šablony položky, název položky **zaměstnanci seznamu**a potom zvolte **přidat** tlačítko.  
  
     Zobrazí se Průvodce nastavením služby SharePoint  
  
11. Na **zvolte nastavení seznamu** stránky, ověřte následující nastavení a potom zvolte **Dokončit** tlačítko:  
  
    1.  **Zaměstnanci seznamu** se zobrazí v **zadejte název chcete k zobrazení seznamu?** pole.  
  
    2.  **Vytvořit seznam přizpůsobitelné na základě:** je přepínač vybrán.  
  
    3.  **Výchozí (prázdný)** je vybrán v **vytvořit seznam přizpůsobitelné na základě:** seznamu.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vytvoří položku seznamu zaměstnanci s sloupec názvu a jedné prázdnou instanci a otevře návrháře seznamu.  
  
12. V Návrháři seznamu na **sloupce** , zvolte **zadejte název nové nebo existující sloupec** řádek a poté přidejte následující sloupce ve **zobrazovaný název sloupce** seznamu:  
  
    1.  Křestní jméno  
  
    2.  společnosti  
  
    3.  Telefon do zaměstnání  
  
    4.  E-mailu  
  
13. Uložte všechny soubory a pak zavřete Editor seznamu.  
  
14. V **Průzkumníku řešení**, rozbalte **zaměstnanci seznamu** uzel a potom rozbalte **instanci seznamu zaměstnanci** podřízený uzel.  
  
15. V *Elements.xml* souboru, nahraďte výchozí XML v tomto souboru následující kód XML. Tato konfigurace XML se změní název v seznamu **zaměstnanci** a přidá informace o zaměstnanec, který má s názvem Jima Hance.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
        <Data>  
          <Rows>  
            <Row>  
              <Field Name="Title">Hance</Field>  
              <Field Name="FirstName">Jim</Field>  
              <Field Name="Company">Contoso</Field>  
              <Field Name="Business Phone">555-555-5555</Field>  
              <Field Name="E-Mail">jim@contoso.com</Field>  
            </Row>  
          </Rows>  
        </Data>  
      </ListInstance>  
    </Elements>  
    ```  
  
16. Uložte a zavřete *Elements.xml* souboru.  
  
17. Otevřete místní nabídky projektu EmployeesListDefinition a zvolte **otevřete** nebo **vlastnosti**.  
  
     Otevře vlastnosti návrháře.  
  
18. Na **SharePoint** zrušte **automaticky odvolat po ladění** zaškrtněte políčko a potom uložte vlastnosti.  
  
#### <a name="to-deploy-the-list-definition-and-list-instance"></a>K nasazení definice seznamu a instanci seznamu  
  
1.  V **Průzkumníku řešení**, vyberte **EmployeesListDefinition** uzel projektu.  
  
2.  V **vlastnosti** okno, ujistěte se, že **aktivní konfigurace nasazení** je nastavena na **výchozí**.  
  
3.  Vyberte **F5** klíče, nebo na řádku nabídek zvolte **ladění** > **spustit ladění**.  
  
4.  Ověřte úspěšně sestavení projektu, že otevře webový prohlížeč na stránku služby SharePoint, **uvádí** zahrnuje nové položky v panelu Snadné spuštění **zaměstnanci** seznamu a že  **Zaměstnanci** seznam obsahuje položku pro Jima Hance.  
  
5.  Zavřete webový prohlížeč.  
  
#### <a name="to-modify-the-list-definition-and-list-instance-and-redeploy-them"></a>K úpravě seznamu definici a instanci seznamu a znovu je  
  
1.  V projektu EmployeesListDefinition, otevřete *Elements.xml* soubor, který je podřízená **instanci seznamu Zaměstnanec** položka projektu.  
  
2.  Odeberte `Data` elementu a její podřízené položky můžete odebrat položku pro Jima Hance ze seznamu.  
  
     Po dokončení soubor by měl obsahovat následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
      </ListInstance>  
    </Elements>  
    ```  
  
3.  Uložte a zavřete *Elements.xml* souboru.  
  
4.  Otevřete místní nabídku pro **zaměstnanci seznamu** položek projektu a potom vyberte **otevřete** nebo **vlastnosti**.  
  
5.  V Návrháři seznamu zvolte **zobrazení** kartě.  
  
6.  V **vybrané sloupce** vyberte **přílohy**a potom zvolte < klíč přesunout tento sloupec **dostupné sloupce** seznamu.  
  
7.  Opakujte předchozí krok pro přesun **Telefon do zaměstnání** sloupec z **vybrané sloupce** se seznam **dostupné sloupce** seznamu.  
  
     Tato akce odebere z výchozí zobrazení těchto polí **zaměstnanci** seznamu na web služby SharePoint.  
  
8.  Spuštění ladění výběrem **F5** klíč, nebo v nabídce panelu Výběr **ladění** > **spustit ladění**.  
  
9. Ověřte, zda **konflikty nasazení** zobrazí se dialogové okno.  
  
     Toto dialogové okno se zobrazí, když Visual Studio se pokusí nasadit řešení (seznam instance) na web služby SharePoint, na kterou již byla nasazena toto řešení. Toto dialogové okno se nezobrazí při spuštění kroku upgradu nasazení později v tomto návodu.  
  
10. V **konflikty nasazení** dialogovém okně vyberte **vyřešit automaticky** tlačítko.  
  
     Visual Studio odstraní instanci seznamu na webu služby SharePoint, nasadí položky seznamu v projektu a pak otevře web služby SharePoint.  
  
11. V **uvádí** části panel Rychlé spuštění, vyberte **zaměstnanci** seznamu a pak ověřte následující podrobnosti:  
  
    -   **Přílohy** a **Telefon domů** sloupce nezobrazí v tomto zobrazení seznamu.  
  
    -   Seznam je prázdný. Při použití **výchozí** konfigurace nasazení k opětovnému nasazení řešení, **zaměstnanci** seznamu byla nahrazena nový prázdný seznam ve vašem projektu.  
  
## <a name="test-the-deployment-step"></a>Testování kroku nasazení
 Nyní jste připraveni k testování v kroku upgradu nasazení. Nejprve přidejte položku do seznamu instance ve službě SharePoint. Změňte definice seznamu a seznamu instanci, je upgradovat na webu služby SharePoint a potvrďte, že krok upgradu nasazení není přepíše novou položku.  
  
#### <a name="to-manually-add-an-item-to-the-list"></a>Ruční přidání položky do seznamu  
  
1.  Na pásu karet na web služby SharePoint v části **nástroje seznamu** , zvolte **položky** kartě.  
  
2.  V **nový** skupiny, vyberte **novou položku**.  
  
     Jako alternativu můžete zvolit **přidat novou položku** odkaz v seznamu položek sám sebe.  
  
3.  V **zaměstnanci - nová položka** okno v **název** zadejte **Správce zařízení**.  
  
4.  V **křestní jméno** zadejte **Andy**.  
  
5.  V **společnosti** zadejte **Contoso**.  
  
6.  Vyberte **Uložit** tlačítko, ověřte, že nová položka se zobrazí v seznamu a pak zavřete webový prohlížeč.  
  
     Dále v tomto návodu budete používat tato položka k ověření, že krok upgradu nasazení není přepsat obsah tohoto seznamu.  
  
#### <a name="to-test-the-upgrade-deployment-step"></a>K testování v kroku nasazení upgradu  
  
1.  V experimentální instanci sady Visual Studio v **Průzkumníku řešení**, otevřete místní nabídku pro **EmployeesListDefinition** uzel projektu a potom zvolte **vlastnosti**.  
  
     Otevře se Editor nebo návrháře vlastnosti.  
  
2.  Na **SharePoint** nastavte **konfigurace nasazení služby Active** vlastnost **upgradu**.  
  
     Konfigurace vlastní nasazení obsahuje nový krok upgradu nasazení.  
  
3.  Otevřete místní nabídku pro **zaměstnanci seznamu** položek projektu a potom vyberte **vlastnosti** nebo **otevřete**.  
  
     Otevře se Editor nebo návrháře vlastnosti.  
  
4.  Na **zobrazení** , zvolte **e-mailu** sloupce a potom zvolte **<** klíč, přesuňte tento sloupec z **vybrané sloupce**se seznam **dostupné sloupce** seznamu.  
  
     Tato akce odebere z výchozí zobrazení těchto polí **zaměstnanci** seznamu na web služby SharePoint.  
  
5.  Spuštění ladění výběrem **F5** klíč, nebo v nabídce panelu Výběr **ladění** > **spustit ladění**.  
  
6.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `CanExecute` metoda.  
  
7.  Vyberte **F5** klíč znovu, nebo v řádku nabídek zvolte **ladění** > **pokračovat**.  
  
8.  Ověřte, že kód zastaví na zarážce, kterou jste nastavili výše v `Execute` metoda.  
  
9. Vyberte **F5** klíče, nebo na řádku nabídek zvolte **ladění** > **pokračovat** poslední čas.  
  
     Otevře se webový prohlížeč web služby SharePoint.  
  
10. V **uvádí** části oblasti Snadné spuštění, vyberte **zaměstnanci** seznamu a pak ověřte následující podrobnosti:  
  
    -   Položka, kterou jste ručně přidali dříve (pro Andy, Správce zařízení) je stále v seznamu.  
  
    -   **Telefon do zaměstnání** a **e-mailovou adresu** sloupce nezobrazí v tomto zobrazení seznamu.  
  
     **Upgrade** konfigurace nasazení upraví stávající **zaměstnanci** instanci seznamu na webu služby SharePoint. Pokud jste použili **výchozí** konfigurace nasazení místo **Upgrade** konfiguraci by dojít ke konfliktu nasazení. Visual Studio by konflikt vyřešit tak, že nahradíte **zaměstnanci** seznamu a položka pro Andy, Správce zařízení by odstraněn.  
  
## <a name="clean-up-the-development-computer"></a>Vyčištění vývojovém počítači
 Po dokončení testování nasazení upgradu krok, odeberte instanci seznamu a definice seznamu z webu služby SharePoint a odeberte rozšíření krok nasazení ze sady Visual Studio.  
  
#### <a name="to-remove-the-list-instance-from-the-sharepoint-site"></a>Chcete-li odebrat instanci seznamu z webu služby SharePoint  
  
1.  Otevřete **zaměstnanci** seznam na webu služby SharePoint, není-li v seznamu již otevřeno.  
  
2.  Na pásu karet na webu služby SharePoint, vyberte **nástroje seznamu** a pak klikněte na příkaz **seznamu** kartě.  
  
3.  V **nastavení** skupiny, vyberte **nastavení seznamu** položky.  
  
4.  V části **oprávnění a správa**, vyberte **odstranit tento seznam** příkaz, zvolte **OK** potvrďte, že chcete odeslat do koše seznamu a pak zavřete webu prohlížeč.  
  
#### <a name="to-remove-the-list-definition-from-the-sharepoint-site"></a>Chcete-li odebrat definice seznamu z webu služby SharePoint  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **sestavení** > **odvolat**.  
  
     Visual Studio odvolá definice seznamu z webu služby SharePoint.  
  
#### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje** > **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **Upgrade kroku nasazení pro projekty SharePoint**a potom zvolte **odinstalovat** příkaz.  
  
3.  V zobrazeném dialogu vyberte **Ano** potvrďte, že chcete odinstalovat rozšíření a potom vyberte **restartovat nyní** k dokončení odinstalace.  
  
4.  Zavřete obě instance sady Visual Studio (experimentální instance a instance sady Visual Studio, ve kterém je otevřen UpgradeDeploymentStep řešení).  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
