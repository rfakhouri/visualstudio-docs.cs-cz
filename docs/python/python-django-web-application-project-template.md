---
title: Šablona webového projektu Django pro Python
description: Přehled šablon sady Visual Studio pro webové aplikace napsané v Pythonu pomocí rozhraní Django.
ms.date: 07/03/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: e20090eec7891de4c199f1f92ec0d0668e0f86e6
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251137"
---
# <a name="django-web-project-template"></a>Šablona webového projektu Django

[Django](https://www.djangoproject.com/) je vysoké úrovně rozhraní Python pro vývoj pro web rychlé, zabezpečené a škálovatelné. Podpora Pythonu v sadě Visual Studio obsahuje několik šablon projektů nastavení struktury Django webové aplikace. Chcete-li použít šablony v sadě Visual Studio, vyberte **souboru** > **nový** > **projektu**, vyhledejte "Django" a vyberte z  **Prázdný webový projekt Django**, **webového projektu Django**, a **Polls – webový projekt Django** šablony. Najdete v článku [Django další kurz](learn-django-in-visual-studio-step-01-project-and-solution.md) návod všechny šablony.

Visual Studio obsahuje plnou podporou technologie IntelliSense pro projekty v Django:

- Kontextové proměnné předaný do šablony:

    ![Technologie IntelliSense pro kontextové proměnné](media/template-django-intellisense.png)

- Značek a filtrování pro obě předdefinované a uživatelem definovanými:

    ![Technologie IntelliSense pro značky a filtry](media/template-django-intellisense-filter.png)

- Barevné zvýrazňování vložených šablon stylů CSS a JavaScript syntaxe:

    ![Šablony stylů CSS, IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio také poskytuje úplný [podporu ladění](debugging-python-in-visual-studio.md) Django projekty: 

![Zarážky](media/template-django-debugging.png)

Je typické Django projektů, které jde spravovat pomocí svých *souboru manage.py* soubor, což je předpoklad, který následuje sady Visual Studio. Chcete-li zrušit pomocí tohoto souboru jako vstupní bod je v podstatě přerušit souboru projektu. V takovém případě budete muset [znovu vytvořit projekt z existujících souborů](managing-python-projects-in-visual-studio.md#create-a-project-from-existing-files) bez označení jako projekt Django.

## <a name="django-management-console"></a>Konzola pro správu Django

Konzole pro správu Django se přistupuje přes různé příkazy na **projektu** nabídek nebo kliknutím pravým tlačítkem myši na projekt v **Průzkumníku řešení**.

- **Otevřete prostředí Django**: otevře prostředí v kontextu vaší aplikace, která umožňuje pracovat s vašimi modely:

    ![Konzola](media/template-django-console-shell.png)

- **Django synchronizace DB**: spustí `manage.py syncdb` v interaktivním okně:

    ![Konzola](media/template-django-console-sync-db.png)

- **Shromažďovat statické**: spustí `manage.py collectstatic --noinput` zkopírovat všechny statické soubory do cesta zadaná položkou `STATIC_ROOT` ve vašich *settings.py*. Když [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md), statické soubory se automaticky shromažďují, jako součást operace publikování.

    ![Konzola](media/template-django-console-collect-static.png)

- **Ověření**: spustí `manage.py validate`, která hlásí chyby ověření v nainstalované modely určené `INSTALLED_APPS` v vaše *settings.py*:

    ![Konzola](media/template-django-console-validate.png)

## <a name="see-also"></a>Viz také:

- [Přečtěte si kurz Django](learn-django-in-visual-studio-step-01-project-and-solution.md)
- [Publikování do Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)