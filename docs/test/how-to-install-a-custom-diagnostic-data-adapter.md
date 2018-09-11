---
title: 'Postupy: instalace vlastního adaptéru diagnostických dat v sadě Visual Studio'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 9d2d6c30696636bc8fd2ca571940ac0165eabbcf
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44321044"
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>Postupy: instalace vlastního adaptéru diagnostických dat

Pokud jste vytvořili vlastního adaptéru diagnostických dat nebo vám byl poskytnut vlastního adaptéru diagnostických dat použít, můžete nainstalovat sestavení adaptéru diagnostických dat zkopírováním souboru sestavení, do správného adresáře na místním počítači.

 Pokud chcete použít pro roli v prostředí vašeho vlastního adaptéru diagnostických dat, musíte nainstalovat adaptér diagnostických dat na všech počítačích, které spustí testovací agenty, které můžete použít pro tuto roli.

 Následujícím postupem nainstalujte vlastní diagnostický adaptér na příslušných místech. Budete potřebovat oprávnění správce na jakýkoli počítač, kam nainstalujete adaptér diagnostických dat.

## <a name="install-a-custom-diagnostic-data-adapter"></a>Instalovat vlastního adaptéru diagnostických dat

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>Chcete-li nainstalovat vlastního adaptéru diagnostických dat

1.  Pokud chcete použít adaptér diagnostických dat při spuštění testů v klientském počítači nebo na počítači agenta, zkopírujte všechny soubory z adresáře sestavení do následující složky v cílovém počítači, na základě instalační cesty:

     *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     Soubory ke kopírování jsou:

    -   Sestavení adaptéru diagnostických dat (*.dll*) (povinné).

    -   Ladění datový soubor (*PDB*) pro adaptér (volitelné).

    -   Konfigurační soubor pro adaptér (`<diagnostic data adapter name>.dll.config`), pokud jste nastavili výchozí nastavení konfigurace (nepovinné).

    -   Sestavení konfiguračního editoru, pokud jste vytvořili pro úpravu nastavení konfigurace pro adaptér (volitelně). Toto je pouze pro klientské počítače. Počítačů agentů nepoužívejte v editoru.

    > [!NOTE]
    > Přestože adaptér diagnostických dat a konfigurační editor lze vytvořit ve stejném projektu a integrované do stejného sestavení, můžete použít samostatné projekty a vytvořit samostatné sestavení, který preferujete.

     Další informace o tom, jak nakonfigurovat nastavení testu pro použití prostředí při spuštění testů, naleznete v tématu [shromažďování diagnostických dat v manuálních testů (testovací plány Azure)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts).

2.  Pokud chcete vybrat adaptér diagnostických dat pro test, musíte nejprve vybrat existující nastavení testu nebo vytvořit nový štítek z Microsoft Test Manager nebo Visual Studio a vybrat adaptér diagnostických dat na **dat a diagnostiky** Karta vybraná nastavení testu.

3.  Pokud máte vytvořen a nainstalován editoru adaptéru diagnostických dat konfigurace, nakonfigurovat adaptér diagnostických dat pro nastavení testu, zvolte **konfigurovat** vedle adaptéru a proveďte libovolné změny. Klikněte na tlačítko **Uložit**. Další informace o tom, jak vytvořit konfigurační editor pro váš kolektor diagnostických dat naleznete v tématu [postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

4.  Pokud spouštíte testy z nástroje Microsoft Test Manager, můžete přiřadit tato nastavení testu do plánu testování před spuštěním testů nebo pomocí **spustit s možnostmi** příkaz pro přidělení nastavení testu a přepsání nastavení testu. Další informace o nastaveních testu naleznete v tématu [shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md).

     Pokud používáte testy ze sady Visual Studio, musíte nastavit tyto jako aktivní nastavení testu. Další informace o nastaveních testu naleznete v tématu [shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md).

5.  Spusťte testy pomocí nastavení testu adaptéru diagnostiky datu.

## <a name="see-also"></a>Viz také:

- [Postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Shromažďování diagnostických údajů pomocí nastavení testů](../test/collect-diagnostic-information-using-test-settings.md)