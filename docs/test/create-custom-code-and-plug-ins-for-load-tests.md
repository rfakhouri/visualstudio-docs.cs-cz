---
title: Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: f6fa3c407e5de4acfe9633bf7c919ba41e2ab3af
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Vytvoření vlastního kódu a modulů plugin pro zátěžové testování

Vlastní modul plug-in používá kód, který lze vytvořit a připojit k zátěžovému testu nebo testu výkonnosti webu. Rozhraní API zátěžového testu a rozhraní API testu výkonnosti webu lze použít k vytvoření vlastních modulů plug-in pro rozšíření integrovaných funkcí. Můžete přidat několik modulů plug-in pro zátěžový test.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Vytvoření modulu Plugin pro zátěžový test vlastní**: rozhraní API testu zatížení můžete vytvořit vlastní modul plug-in pro přidání více testování funkcí zátěžový test.|-   [Postupy: použití rozhraní API zátěžového testu](../test/how-to-use-the-load-test-api.md)<br />-   [Postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md)|
|**Vytvořit vlastní modul plug-in pro svůj test výkonu webů:** webového rozhraní API testu výkonu můžete vytvořit vlastní modul plug-in pro přidání další testování funkcí vaší testu výkonnosti webu, včetně na úrovni požadavku. Lze také vytvořit test webové služby.<br /><br /> Mimo to lze vytvořit modul plug-in zapisovače webu, který může upravovat test výkonnosti webu poté, co byl zaznamenán, ale před tím, než se zobrazí v Prohlížeči výsledků testů výkonu webu.|-   [Postupy: použití rozhraní API testu výkonnosti webu](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Postupy: vytvoření modulu Plugin pro Test výkonnosti webu](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Postupy: vytvoření modulu Plugin úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Postupy: vytvoření testu webové služby](../test/how-to-create-a-web-service-test.md)<br />-   [Postupy: vytvoření modulu Plugin rekordéru](../test/how-to-create-a-recorder-plug-in.md)|
|**Přidání funkcí uživatelského rozhraní pro prohlížeč výsledků testu výkonnosti webu:** můžete přidat další funkce uživatelského rozhraní pomocí přidat v sadě Visual Studio prohlížeč výsledků testu webu výkonu.|-   [Postupy: Vytvoření doplňku sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Vytvoření vlastní text HTTP editoru:** můžete vytvořit vlastní editor Upravit binární nebo řetězec odpovědi XML http z webové služby.|-   [Postupy: vytvoření vlastního editoru těla HTTP pro Editor testu výkonnosti webu](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Odkaz

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)