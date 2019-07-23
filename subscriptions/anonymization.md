---
title: Anonymita dat předplatitele sady Visual Studio | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/19/2019
ms.topic: conceptual
description: Přečtěte si, jak se data předplatitelů při ztrátě přístupu k předplatným nezdařila.
ms.openlocfilehash: 8ba1a462083281c2228f2d6e25c42485ead8aa19
ms.sourcegitcommit: 485881e6ba872c7b28a7b17ceaede845e5bea4fe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2019
ms.locfileid: "68377959"
---
# <a name="anonymization-of-visual-studio-subscriber-information"></a>Anonymita informací předplatitele sady Visual Studio
Když dojde k události, která blokuje použití předplatného předplatitele, jako je například vypršení platnosti předplatného nebo odstranění přihlašovacího účtu odběratele, osobní údaje uživatele, například jméno a přihlašovací účet, jsou v podstatě zakódované pro vykreslování. nepoužitelné.  Tento postup slouží k ochraně osobních údajů předplatitele.

[!INCLUDE [GDPR-related guidance](includes/gdpr-intro-sentence.md)]

## <a name="when-does-anonymization-occur"></a>Kdy dojde k anonymitě?
Události, které vygenerují předplatné nepoužité pro předplatitele, aktivují anonymitu.  Jak rychle probíhá, závisí na typu předplatného a události triggeru. Další informace najdete v následující tabulce.

| Typ předplatného                                                                                                                       | Událost aktivující anonymitu                                                                                                     | Když dojde k anonymitě |
|-----------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------|
| Visual Studio Dev Essentials                                                                                                            | Předplatitelský výslovný z programu nebo nepřijímá podmínky použití                                    | 30 dní               |
| Předplatná sady Visual Studio zakoupená prostřednictvím Microsoft Store (maloobchodní)                                                                      | Předplatné vyprší nebo není aktivované.                                                                   | 360 dní                  |
| Předplatná sady Visual Studio získaná prostřednictvím multilicenčního programu, Visual Studio Marketplace (odběry cloudu) nebo programy jako MPN | Předplatné vyprší nebo není přiřazeno uživateli.                                                          | 180 dní                  |
| Všechna předplatná                                                                                                                       | Zavře se účet Azure Active Directory nebo účet Microsoft (MSA), který se používá k přihlášení k předplatnému. | Hned               |
| Všechna předplatná                                                                                                                       | Předplatitel se odebere z klienta, který je přidružený k Azure Active Directorymu účtu.                                | Hned               |

## <a name="faq"></a>Nejčastější dotazy
### <a name="q--does-the-anonymization-of-the-subscribers-personal-information-cause-them-to-lose-access-to-the-subscription"></a>Č  Způsobuje anonymita osobních údajů předplatitele ztrátu přístupu k předplatnému?
O:  Ne.  Anonymita je v reakci na událost, která způsobuje ztrátu přístupu k předplatnému, ale nezpůsobí přístup k tomuto předplatnému.

### <a name="q--im-an-administrator-for-my-organizations-subscriptions--if-one-of-my-subscribers-information-is-anonymized-can-that-subscription-be-reassigned-to-another-user"></a>Č  Jsem správcem předplatných mojí organizace.  Pokud je jedna z informací o mém předplatiteli anonymá, může se předplatné znovu přiřadit jinému uživateli?
O:  Ano – Pokud platnost předplatného nevypršela, je možné ji přiřadit jinému předplatiteli.

## <a name="next-steps"></a>Další kroky
Přečtěte si, jak se vyhnout anonymitě pomocí [propojení MSA a identit AAD](/azure/active-directory/b2b/add-users-administrator).
