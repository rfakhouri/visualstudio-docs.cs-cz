---
title: "Postupy: publikování projektu s konkrétním národním prostředím | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 48ad25fd215ae9485420b3fbbfa9ac3cd41b8827
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>Postupy: Publikování projektu s konkrétním národním prostředím
Je běžné pro aplikaci tak, aby obsahovala součásti, které mají různá národní prostředí. V tomto scénáři by vytvářet řešení, která má několik projektů a pak publikovat samostatné projekty pro každé národní prostředí. Tento postup ukazuje, jak pomocí makra publikování první projekt v řešení s použitím národního prostředí "en". Pokud chcete vyzkoušet tuto proceduru s národním prostředím než "en", nezapomeňte nastavit `localeString` v makru na odpovídající národního prostředí, který používáte (pro příklad, "de" nebo "de-DE").  
  
> [!NOTE]
>  Při použití této makro umístění publikování musí být platná adresa URL nebo Universal Naming Convention (UNC) sdílené složky. Navíc Internetové informační služby (IIS) musí být nainstalovaná ve vašem počítači. Instalace služby IIS, na **spustit** nabídky, klikněte na tlačítko **ovládací panely**. Klikněte dvakrát na **přidat nebo odebrat programy**. V **přidat nebo odebrat programy**, klikněte na tlačítko **přidat nebo odebrat součásti systému Windows**. V **Průvodce součástmi systému Windows**, vyberte **Internetové informační služby (IIS)** zaškrtávací políčko **součásti** seznamu. Pak klikněte na tlačítko **Dokončit** zavřete průvodce.  
  
### <a name="to-create-the-publishing-macro"></a>K vytvoření publikování makra  
  
1.  Otevřete Průzkumníka maker na **nástroje** nabídce přejděte na **makra**a potom klikněte na **Průzkumník maker**.  
  
2.  Vytvoření nového makra. V Průzkumníku maker vyberte **Moje makra**. Na **nástroje** nabídky, přejděte na příkaz **makra**a potom klikněte na **nového makra**. Název modulu **PublishSpecificCulture**.  
  
3.  V Průzkumníku maker rozbalte **Moje makra** uzel a potom otevřete **publikovat všechny projekty poklikáním** modulu poklepáním (nebo z **nástroje** nabídky, přejděte na příkaz **Makra**a potom klikněte na **makra IDE**).  
  
4.  V prostředí IDE makra, přidejte následující kód do modulu, po `Import` příkazy:  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certficate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5.  Zavřete makra IDE. Pak se fokus vrátí do sady Visual Studio.  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>Chcete-li publikovat projekt pro specifické národní prostředí  
  
1.  K vytvoření projektu jazyka Visual Basic aplikace systému Windows, na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, vyberte **aplikace Windows** z **jazyka Visual Basic** uzlu. Název projektu **PublishLocales**.  
  
3.  Klikněte na tlačítko Form1. V **vlastnosti** okno, v části **návrhu**, změnit **jazyk** vlastnost z **(výchozí)** k **Angličtina**. Změna **Text** vlastnost formuláře **MyForm**.  
  
     Všimněte si, že lokalizovaný prostředek knihovny DLL se nevytvoří, dokud jsou potřeba. Například jsou vytvořeny při změně textu formuláře nebo jeden z jeho ovládacích prvků po zadání nové národní prostředí.  
  
4.  Publikování PublishLocales pomocí prostředí Visual Studio IDE.  
  
     V **Průzkumníku**, zvolte PublishLocales. Na **projektu** nabídce vyberte možnost **vlastnosti**. V Návrháři projektu na **publikovat** stránky, zadejte umístění pro publikování **http://localhost/PublishLocales**a potom klikněte na **publikovat**.  
  
     Jakmile se zobrazí webová stránka publikování, zavřete ji. (Pro tento krok, budete muset publikování tohoto projektu, není nutné ji nainstalovat.)  
  
5.  Znovu publikujte PublishLocales vyvoláním makra v okně příkazového řádku Visual Studia. Chcete-li zobrazit okno příkazového řádku, na **zobrazení** nabídky, přejděte na příkaz **ostatní okna** a pak klikněte na **příkazové okno**, nebo stiskněte klávesu CTRL + ALT + A. V okně příkazového řádku zadejte `macros`; automatické dokončování poskytne seznam dostupných makra. Vyberte následující makro a stiskněte klávesu ENTER:  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6.  Pokud je proces publikování úspěšná, vygeneruje se zpráva s oznámením "publikování byl úspěšný pro PublishLocales\PublishLocales.vbproj. Publikování jazyk byl "en". " Klikněte na tlačítko **OK** do pole zpráva. Jakmile se zobrazí webová stránka publikování, klikněte na tlačítko **nainstalovat**.  
  
7.  Vyhledejte v C:\Inetpub\wwwroot\PublishLocales\en. Měli byste vidět nainstalované soubory například manifesty, setup.exe a soubor publikovat webovou stránku, kromě lokalizované DLL prostředků. (Ve výchozím nastavení ClickOnce přidá příponu .deploy soubory .exe a knihovny DLL, můžete odebrat toto rozšíření po nasazení.)  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Makra vývojového prostředí](http://msdn.microsoft.com/en-us/d23105d8-34fe-4ad9-8278-fae2c660aeac)   
 [Okno Průzkumníka – makro](http://msdn.microsoft.com/en-us/762169e6-f83f-44b4-bffa-d0f107cae9a3)   
 [Postupy: úprava a vytváření makra prostřednictvím kódu programu](http://msdn.microsoft.com/en-us/6716f820-1feb-48ad-a718-27eb6b473c5a)