---
title: Ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, debugging extensions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e170a5ed703a9bf5aae2e73126de52ecf88e8084
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443517"
---
# <a name="debug-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio
  Můžete ladit rozšíření nástrojů SharePoint v experimentální instanci nebo pravidelné instanci aplikace Visual Studio. Pokud je potřeba Poradce při potížích s chováním rozšíření, můžete také změnit hodnoty registru, chcete-li zobrazit další informace o chybě a nakonfigurujte, jak Visual Studio provede příkazy serveru SharePoint.

## <a name="debug-extensions-in-the-experimental-instance-of-visual-studio"></a>Ladění rozšíření v experimentální instanci sady Visual Studio
 K ochraně vašeho vývojového prostředí Visual Studio před náhodným poškozením netestovaným rozšířením poskytuje Visual Studio SDK alternativní instanci aplikace Visual Studio, volá se, *experimentální instanci*, které můžete použít instalace a testování rozšíření. Nová rozšíření vyvíjíte pomocí pravidelných instance sady Visual Studio, ale ladíte a spouštíte je v experimentální instanci aplikace. Další informace najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).

 Pokud je k nasazení vašeho rozšíření použit projekt VSIX a projekt VSIX je projekt po spuštění ve vašem řešení, Visual Studio automaticky nainstaluje a spustí rozšíření v experimentální instanci při ladění vašeho řešení. Projekt spuštění je projekt, který se spustí při ladění řešení, které obsahuje více projektů. Další informace o použití projektu VSIX k nasazení vašeho rozšíření naleznete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

 Příklady, které ukazují, jak ladit různé typy rozšíření v experimentální instanci sady Visual Studio najdete v následujících návodech:

- [Návod: Rozšíření typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)

- [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)

- [Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)

- [Návod: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)

- [Návod: Volání do objektového modelu klienta SharePoint v rozšíření Průzkumníka serveru](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)

## <a name="debug-extensions-in-the-regular-instance-of-visual-studio"></a>Ladění rozšíření v normální instanci aplikace Visual Studio
 Pokud chcete ladit vaše rozšíření projektu v normální instanci aplikace Visual Studio, nejprve instalujte rozšíření v normální instanci aplikace. Potom připojte ladicí program k druhému procesu Visual Studio. Jakmile budete hotovi, můžete odebrat rozšíření tak, aby už nenačte na vývojovém počítači.

#### <a name="to-install-the-extension"></a>Chcete-li nainstalovat rozšíření

1. Zavřete všechny instance sady Visual Studio.

2. Ve výstupní složce sestavení pro projekt rozšíření otevřete *VSIX* souboru poklepáním nebo otevřením jeho místní nabídku a následným výběrem možnosti **otevřete**:

3. V **instalační program rozšíření sady Visual Studio** dialogového okna zvolte edici sady Visual Studio, do kterého chcete nainstalovat rozšíření a klikněte na tlačítko **nainstalovat** tlačítko.

     Visual Studio nainstaluje soubory rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions\\*jméno autora*\\*název rozšíření* \\ *verze*. Poslední tři složky v této cestě se vytvářejí na základě `Author`, `Name`, a `Version` prvky *extension.vsixmanifest* souboru rozšíření.

4. Poté, co Visual Studio nainstaluje rozšíření, vyberte **Zavřít** tlačítko.

#### <a name="to-debug-the-extension"></a>Chcete-li ladit rozšíření

1. Otevřít Visual Studio s oprávněními správce a otevřete projekt rozšíření. Následující kroky odkazují na tuto instanci sady Visual Studio, jako *první instance*.

2. Spusťte jinou instanci aplikace Visual Studio s oprávněními správce. Následující kroky odkazují na tuto instanci sady Visual Studio, jako *druhou instanci*.

3. Přepněte na první instanci sady Visual Studio.

4. V panelu nabídky zvolte **ladění**, **připojit k procesu**.

5. V **procesy k dispozici** klikněte na položku *devenv.exe*. Tato položka odkazuje na druhou instanci aplikace Visual Studio; To je instanci, kterou chcete ladit rozšíření vašeho projektu.

6. Zvolte **připojit** tlačítko.

     Visual Studio spustí rozšíření projektu v režimu ladění.

7. Přepněte na druhou instanci sady Visual Studio.

8. Vytvoření nového projektu služby SharePoint, který načte rozšíření. Například pokud ladění rozšíření pro položky projektu definice seznamu, vytvořte **definice seznamu** projektu.

9. Provádění jakýchkoli kroků je nezbytné pro testování kódu rozšíření.

10. Po dokončení ladění rozšíření zavřete druhou instanci aplikace Visual Studio.

#### <a name="to-remove-the-extension"></a>Odebrat rozšíření

1. V sadě Visual Studio v panelu nabídek zvolte **nástroje**, **rozšíření a aktualizace**.

     **Rozšíření a aktualizace** zobrazí se dialogové okno.

2. V seznamu rozšíření zvolte název rozšíření a klikněte na tlačítko **odinstalovat** tlačítko.

3. V dialogovém okně, které se zobrazí, zvolte **Ano** potvrďte, že chcete odinstalovat rozšíření.

4. Zvolte **restartovat nyní** tlačítko pro dokončení odinstalace.

## <a name="debug-sharepoint-commands"></a>Ladění příkazů služby SharePoint
 Pokud chcete ladit příkaz SharePoint, který je součástí rozšíření nástrojů služby SharePoint, je nutné připojit ladicí program *vssphost4.exe* procesu. To je 64bitový hostitelský proces, který provede příkazy serveru SharePoint. Další informace o příkazech SharePoint a *vssphost4.exe*, naleznete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).

#### <a name="to-attach-the-debugger-to-the-vssphost4exe-process"></a>Chcete-li připojit ladicí program k procesu vssphost4.exe

1. Spusťte ladění rozšíření v experimentální instanci sady Visual Studio nebo normální instanci aplikace Visual Studio podle výše uvedených pokynů.

2. V instanci aplikace Visual Studio, ve které používáte ladicí program, na panelu nabídek zvolte **ladění**, **připojit k procesu**.

3. V **procesy k dispozici** klikněte na položku *vssphost.exe*.

    > [!NOTE]
    > Pokud se vssphost.exe v seznamu nezobrazí, je nutné spustit *vssphost4.exe* zpracovat v instanci aplikace Visual Studio, ve kterém jsou spuštěna rozšíření. Obvykle to provedete pomocí provádí akci, která způsobí, že Visual Studio pro připojení k webu služby SharePoint ve vývojovém počítači. Například Visual Studio spustí *vssphost4.exe* po rozbalení uzlu připojení k webu (uzel, který zobrazuje adresu URL webu) pod **připojení služby SharePoint** uzlu **Průzkumníka serveru**  okna, nebo když přidáte určité položky projektu služby SharePoint, jako například **instanci seznamu** nebo **příjemce událostí** položky projektu služby SharePoint.

4. Zvolte **připojit** tlačítko.

5. V instanci aplikace Visual Studio, která je právě laděna proveďte kroky, které jsou nutné pro provedení příkazu.

## <a name="modify-registry-values-to-help-debug-sharepoint-tools-extensions"></a>Změnit hodnoty registru pro ladění rozšíření nástrojů SharePoint
 Při ladění rozšíření nástrojů SharePoint v sadě Visual Studio můžete změnit hodnoty v registru při odstraňování rozšíření. Hodnoty existují v **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools** klíč. Tyto hodnoty neexistují ve výchozím nastavení.

 Abychom pomohli řešit potíže jakéhokoli rozšíření nástrojů služby SharePoint, můžete vytvořit a nastavit hodnotu EnableDiagnostics. Následující tabulka popisuje tuto hodnotu.

|Value|Popis|
|-----------|-----------------|
|EnableDiagnostics|REG_DWORD, která určuje, zda jsou diagnostické zprávy zobrazeny v **výstup** okna.<br /><br /> Chcete-li zobrazit diagnostické zprávy, nastavte tuto hodnotu na 1. Chcete-li ukončit zobrazování zpráv, nastavte tuto hodnotu na 0 nebo tuto hodnotu odstraňte.<br /><br /> Pro zapisování zpráv do **výstup** rozšíření nástrojů okna ze Sharepointu, použijte službu projektu SharePoint. Další informace najdete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).|

 Pokud vaše rozšíření obsahuje příkaz SharePoint, můžete vytvořit a nastavit další hodnoty, které vám pomohou vyřešit příkazu. Následující tabulka popisuje tyto hodnoty.

|Value|Popis|
|-----------|-----------------|
|AttachDebuggerToHostProcess|REG_DWORD, která určuje, jestli se má zobrazit dialogové okno, která umožňuje připojit ladicí program k *vssphost4.exe* ihned po jeho spuštění. To je užitečné, pokud příkaz, který chcete ladit, je spuštěn ve vssphost.exe ihned po svém spuštění a není k dispozici dostatek času ručně připojit ladicí program před provedením příkazu. Chcete-li zobrazit dialogové okno, *vssphost4.exe* volání <xref:System.Diagnostics.Debugger.Break%2A> při spuštění metodu.<br /><br /> Pokud chcete povolit toto chování, nastavte tuto hodnotu na 1. Chcete-li toto chování vypnout, nastavte tuto hodnotu na 0 nebo tuto hodnotu odstraňte.<br /><br /> Pokud nastavíte tuto hodnotu na 1, můžete také chtít zvýšit hodnotu HostProcessStartupTimeout, abyste měli dostatek času na připojení ladicího programu, než se očekává, že Visual Studio *vssphost4.exe* signál, že je úspěšně spuštěn.|
|ChannelOperationTimeout|REG_DWORD, která určuje dobu v sekundách, po který Visual Studio čeká na provedení příkazu SharePoint. Pokud příkaz nespustí včas, <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> je vyvolána výjimka.<br /><br /> Výchozí hodnota je 120 sekund.|
|HostProcessStartupTimeout|REG_DWORD, která určuje dobu v sekundách, že Visual Studio čeká *vssphost4.exe* signál, že je úspěšně spuštěn. Pokud *vssphost4.exe* nevydá signál úspěšné spuštění v čase, <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> je vyvolána výjimka.<br /><br /> Výchozí hodnota je 60 sekund.|
|MaxReceivedMessageSize|REG_DWORD, která určuje maximální povolenou velikost v bajtech zpráv WCF, které jsou předávány mezi Visual Studio a *vssphost4.exe*.<br /><br /> Výchozí hodnota je 1 048 576 bajtů (1 MB).|
|MaxStringContentLength|REG_DWORD, která určuje maximální povolenou velikost v bajtech řetězců, které jsou předávány mezi Visual Studio a *vssphost4.exe*.<br /><br /> Výchozí hodnota je 1 048 576 bajtů (1 MB).|

## <a name="see-also"></a>Viz také:

- [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)
- [Nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)
