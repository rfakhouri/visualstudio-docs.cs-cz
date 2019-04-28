---
title: 'Postupy: Zákaz aktivace adresy URL aplikací ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6841b8a91cec24f467f6e3f684cbb27e25c9fa63
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62899346"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Postupy: Zákaz aktivace adresy URL aplikací ClickOnce

Obvykle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí ihned po jeho instalaci z webového serveru. Z bezpečnostních důvodů se můžete rozhodnout pro toto chování zakázat a že se uživatelé ke spuštění aplikace z **Start** nabídky místo. Následující postup popisuje, jak zákaz aktivace adresy URL.

Tento postup lze použít pouze pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nainstalované v počítači uživatele z webového serveru. Nelze použít pro online jen pro aplikace, které lze spustit pouze pomocí jejich adresy URL. Další informace o rozdílu mezi pouze v režimu online a nainstalované aplikace najdete v tématu [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).

Tento postup používá Windows Software Development Kit (SDK) nástroje MageUI.exe. Další informace o tomto nástroji najdete v tématu [MageUI.exe (Manifest Generation and Editing Tool, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Můžete také provést tento postup pomocí sady Visual Studio.

## <a name="procedure"></a>Postup

### <a name="to-disable-url-activation-for-your-application"></a>Chcete-li zákaz aktivace adresy URL pro vaši aplikaci

1. Otevření manifestu nasazení v MageUI.exe. Pokud jste ještě nevytvořili, jednu, postupujte podle kroků v [názorný postup: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).

2. Vyberte **možnosti nasazení** kartu.

3. Zrušte **automaticky spustit po instalaci aplikace** zaškrtávací políčko.

4. Uložit a podepsání manifestu.

## <a name="see-also"></a>Viz také:

- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)