---
title: Úvod do Azure Functions
description: Pomocí Azure functions v sadě Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 25CD47A4-5B32-4734-8EF3-E24A02AABF29
ms.openlocfilehash: 5d787efbd09ad7f2d4a1f5f72b8f1493d8c6c587
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33871086"
---
# <a name="introduction-to-azure-functions"></a>Úvod do Azure Functions

Azure functions je způsob, jak vytvářet a spouštět událostmi řízené fragmenty kódu – – funkce – – v cloudu, aniž by bylo nutné explicitně zřizovat nebo spravovat infrastrukturu. Další informace o Azure Functions najdete v tématu [dokumentace Azure Functions](https://docs.microsoft.com/azure/azure-functions/).

## <a name="requirements"></a>Požadavky

Jsou součástí nástroje Azure funkce **Visual Studio pro Mac 7.5**.

Pokud chcete vytvořit a nasadit funkce budete potřebovat předplatné Azure, která je k dispozici zdarma z [ https://azure.com/free ](https://azure.com/free).

## <a name="creating-your-first-azure-functions-project"></a>Vytvoření prvního projektu Azure Functions

1. V sadě Visual Studio pro Mac, vyberte **soubor > Nový řešení...** 
2. Z tohoto dialogového okna Nový projekt, vyberte šablonu Azure Functions v části **cloudu > Obecné** a klikněte na tlačítko **Další**:

    ![Dialogové okno Nový projekt zobrazující možnost Azure functions](media/azure-functions-image1.png)

3. Zadejte **název projektu** a vyberte **vytvořit**.

Visual Studio pro Mac vytvoří .NET Standard projekt s funkcí HttpTrigger výchozí zahrnuty. Zahrnuje také NuGet odkazy na celou řadu **AzureWebJobs** balíčky, a taky **Newtonsoft.Json** balíčku.

![Visual Studio pro Mac editor zobrazení zbrusu novou funkci azure ze šablony](media/azure-functions-newproj.png)

Nový projekt obsahuje následující soubory:

* **HttpTrigger.cs** – Tato třída obsahuje často používaný kód pro funkce aktivované protokolem HTTP. Obsahuje **%{FunctionName/** atribut s názvem funkce a atribut aktivační událost **HttpTrigger**, který určuje, že funkce se aktivuje požadavkem HTTP. Další informace o metodě funkce, najdete v části [Azure funkcí jazyka C# referenční informace pro vývojáře](https://docs.microsoft.com/azure/azure-functions/functions-dotnet-class-library) článku.
* **Host.JSON** – tento soubor popisuje možnosti globální konfiguraci pro funkce hostitele. Příklad souboru a informace o nastavení k dispozici pro tento soubor najdete v tématu [host.json odkazu pro Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-host-json).
* **Local.Settings.JSON** – tento soubor obsahuje všechna nastavení pro spouštění funkce místně. Tato nastavení jsou používány nástroje základní funkce Azure. Další informace najdete v tématu [nastavení místního souboru](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local#local-settings-file) v článku nástroje základní funkce Azure.

Teď, když jste vytvořili nový projekt Azure Functions v sadě Visual Studio pro Mac, je otestování výchozí funkce aktivované protokolem HTTP z místního počítače.

<!--
## Create an Azure storage account

[Describe why this step is necessary and what it does]

1. Log on to your account at [https://portal.azure.com](https://portal.azure.com).
2. Under the **Favorites** section, located on the left of the screen, select **Storage Accounts**:
    ![]()
3. Select **Add** to create a new storage account:
    ![]()
4. Enter a globally unique name for the **Name** and reuse it for the **Resource group**. You can keep all the other items as their default.
    ![]()
5. Click **Create**. It might take a few minutes to create the storage account. You'll get a notification once it has been successfully created.
6. Select the **Go to resource** button from the notification:
    ![]()
-->

## <a name="testing-the-function-locally"></a>Testování funkce místně

S podporou Azure Functions v sadě Visual Studio pro Mac můžete testování a ladění funkce ve svém místním vývojovém počítači.

1. Chcete-li funkci lokálně otestovat, stiskněte **spustit** tlačítko v sadě Visual Studio pro Mac:

    ![Spustit ladění – tlačítko v sadě visual studio pro mac](media/azure-functions-run.png)

1. Spuštění projektu spustí místní ladění na funkci Azure a otevře nové okno terminálu, jak je znázorněno na následujícím obrázku: 

    ![okno terminálu zobrazuje funkce výstup](media/azure-functions-terminal.png) 

    Zkopírujte adresu URL z výstupu.

3. Vložte adresu URL pro požadavek HTTP do panelu Adresa prohlížeče. Přidat řetězec dotazu `?name=<yourname>` na konec adresy URL a provedení požadavku. Následující obrázek ukazuje odpovědi v prohlížeči místní požadavek GET vráceným funkcí:

    ![požadavek HTTP v prohlížeči](media/azure-functions-httpreq.png)

## <a name="creating-a-new-function"></a>Vytvoření nové funkce

Funkce šablony umožňují rychle vytvořit nové funkce použitím nejběžnější aktivační události a šablon. Když je vytvořen nový projekt Azure Functions, automaticky zahrne HttpTrigger funkce. Pokud chcete vytvořit jiný typ funkce, postupujte takto:

1. Odeberte **HttpTrigger.cs** soubor pravým tlačítkem myši na něm a výběrem **odebrat**. Následující výstraha, vyberte **odstranit** jeho odebrání z projektu:

    ![Dialogové okno odeberete soubory z projektu](media/azure-functions-remove.png)

2. Chcete-li přidat novou funkci, klikněte pravým tlačítkem na název projektu a vyberte **Přidat > přidat funkci...** :

    ![kontext akce pro přidání nové funkce](media/azure-functions-addnew.png)

3. Z **nové funkce Azure** dialogovém okně, vyberte funkci, budete potřebovat:

    ![Dialogové okno Nový azure – funkce](media/azure-functions-newfunction.png)

    Seznam šablon funkce Azure, které jsou uvedeny v následující části.

## <a name="available-function-templates"></a>K dispozici funkce šablon

- **HTTP** – aktivace provádění kódu pomocí požadavku HTTP. Existují explicitní šablon pro následující aktivace protokolu HTTP:
    - CRUD GET protokolu HTTP
    - CRUD POST protokolu HTTP
    - Aktivace protokolu HTTP s parametry
    - Aktivace protokolu HTTP
- **Časovač** – provést čištění nebo jiných dávkových úkolů podle předdefinovaného plánu. Tato šablona má dvě pole: název a plánu, který je výraz CRON šesti pole. Další informace najdete v tématu [Azure functions článek na čas](https://docs.microsoft.com/azure/azure-functions/functions-create-scheduled-function)
- **Aktivační událost Githubu** – reakce na události, které nastaly v úložištích Githubu. Další informace najdete v tématu [Azure Functions článku na Githubu](https://docs.microsoft.com/azure/azure-functions/functions-create-github-webhook-triggered-function)
    - GitHub commenter – tato funkce se spustí při přijetí webhook Githubu pro požadavek na problém nebo přijetí změn a přidá komentář.
    - WebHook Githubu – tato funkce se spustí, když obdrží webhook Githubu
- **Objekt BLOB aktivační událost** – po jejich přidání do kontejneru objektů BLOB Azure Storage procesu. Vedle názvu funkce této šablony trvá také vlastnost cestu a připojení. Vlastnost cesty je cestu v rámci účtu úložiště, který bude sledovat aktivační událost. Účet připojení je název nastavení aplikace obsahující váš připojovací řetězce k účtu úložiště. Další informace najdete v tématu [článku úložiště objektů Blob Azure functions](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-blob-triggered-function).
- **Ve frontě aktivační události** – to je funkce, která bude odpovídat na zprávy přicházející do fronty Azure Storage. Vedle názvu funkce trvá této šablony **cesta** (název fronty, ze kterého budou číst zprávy) a účet úložiště **připojení** (název nastavení aplikace, který obsahuje úložiště připojovací řetězce k účtu). Další informace najdete v tématu [Azure functions článek na Queue Storage](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-queue-triggered-function).
- **Obecný WebHook** – to je jednoduché funkce, která se spustí pokaždé, když obdrží žádost z jakoukoli službu, která podporuje webhooky. Další informace najdete v tématu [Azure functions článek na obecné webhooky](https://docs.microsoft.com/azure/azure-functions/functions-create-generic-webhook-triggered-function)
- **Úprava velikosti obrázku** – tato funkce vytvoří změněnou bitové kopie vždy, když je přidána do objektu blob do kontejneru. Šablony trvá cestu a připojovací řetězec pro aktivační událost, malý obrázek výstup a výstup střední bitové kopie.
- **SAS token** – tato funkce generuje token SAS pro daný název kontejneru a objektů blob Azure Storage. Vedle názvu funkce této šablony trvá také vlastnost cestu a připojení. Vlastnost cesty je cestu v rámci účtu úložiště, který bude sledovat aktivační událost. Účet připojení je název nastavení aplikace obsahující váš připojovací řetězce k účtu úložiště. **Přístupová práva** také je nutné nastavit. Úroveň oprávnění řídí, jestli funkce vyžaduje klíč rozhraní API a který klíč se použije. Funkce používá funkce klíč; Správce používá hlavní klíč. Další informace najdete v tématu [C# funkce Azure pro generování tokeny SAS](https://azure.microsoft.com/resources/samples/functions-dotnet-sas-token/) ukázka.
- **Trvanlivý funkce orchestration** – trvanlivý funkce umožňují zapsat stavové funkce v prostředí bez serveru. Rozšíření spravuje stav, kontrolní body a restartování za vás. Další informace najdete v tématu příručky Azure functions na [trvanlivý funkce](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)