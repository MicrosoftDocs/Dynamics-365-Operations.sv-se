---
title: Konfigurera Azure Active Directory-autentisering för kassainloggning
description: I denna artikel beskrivs hur du konfigurerar Azure Active Directory som autentiseringsmetod i Microsoft Dynamics 365 Commerce-kassan.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 47da2c78cef2bbee324fbc2202898fbabd927c4d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853938"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Konfigurera Azure Active Directory-autentisering för kassainloggning

[!include [banner](includes/banner.md)]

I denna artikel förklaras hur du konfigurerar Azure Active Directory (Azure AD) som autentiseringsmetod i Microsoft Dynamics 365 Commerce-kassan (POS).

Återförsäljare som använder Dynamics 365 Commerce tillsammans med andra molnbaserade Microsoft-tjänster som exempelvis Microsoft Azure, Microsoft 365 och Microsoft Teams vill vanligtvis använda Azure AD för central hantering av användarreferenser för en säker och sömlös inloggningsupplevelse för alla program. Om du vill använda Azure AD-autentisering för Commerce POS måste du först konfigurera Azure AD som autentiseringsmetod i Commerce headquarters.

## <a name="configure-pos-authentication-method"></a>Konfigurera metod för kassaautentisering

Följ dessa steg för att konfigurera metoden för kassaautentisering i Commerce headquarters.
    
1. Öppna **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler** och välj en funktionsprofil som du vill ändra.
1. I avsnittet **Inloggning för butikspersonal** i snabbfliken **Funktioner** väljer du ett alternativ för autentiseringsmetod i listrutan **Metod för inloggningsmetod**.

    **Metoden för inloggningsautentisering** har tre alternativ:
    
    - **Personal-ID och lösenord** – För det här standardalternativet måste kassaanvändarna ange ett personal-ID och ett lösenord för att logga in i kassan och för att få åtkomst till åsidosättningsfunktionen för hanterare.
    - **Azure AD utan enkel inloggning** – Det här alternativet kräver att kassaanvändarna använder Azure AD-autentiseringsuppgifter för att logga in i kassan och få åtkomst till åsidosättningsfunktionen för hanterare. När kassaklienten uppdateras eller öppnas igen måste kassaanvändaren ange autentiseringsuppgifter för Azure AD för att kunna logga in igen.
    - **Azure AD med enkel inloggning** – När det här alternativet har valts kan POS-användare logga in i Molnbaserad pos (CPOS) med aktiva Azure AD-autentiseringsuppgifter som används av andra webbprogram i samma webbläsare, eller logga in på Modern POS (MPOS) med hjälp av Azure AD-autentiseringsuppgifter registrerade i Windows. Båda metoder gör att du kan logga in utan att ange Azure AD-autentiseringsuppgifter på inloggningsskärmen för kassa. Åtkomst till funktionen för åsidosättning för kassahanterare kräver dock fortfarande inloggning med Azure AD-autentiseringsuppgifter.

1. Gå till **Retail och Commerce > Retail och Commerce IT > Distributionsschema** och kör jobbet **1070 (kanalkonfiguration)** för att synkronisera de senaste funktionsprofilinställningarna med kassaklienter.

> [!NOTE]
> - Autentiseringen **Azure AD utan enkel inloggning** ersätter alternativet **Azure Active Directory** i Commerce version 10.0.18 och tidigare.
> - Azure AD-autentisering kräver en aktiv Internetanslutning och fungerar inte när kassan är offline.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Associera Azure AD-konton med kassaanvändare

Om du vill använda Azure AD som autentiseringsmetod för kassa måste du koppla Azure AD-konton med kassaanvändare i Commerce headquarters. 

Om du vill koppla Azure AD-konton till kassaanvändare i Commerce headquarters följer du dessa steg.
    
1. Gå till **Retail och Commerce > Medarbetare > medarbetare** och öppna en medarbetarpost.
1. I åtgärdsfönstret väljer du fliken **Commerce** och sedan, under **Extern identitet**, markerar du **Associera befintlig identitet**. 
1. I dialogrutan **Använd befintlig extern identitet**, välj **Sök med e-post**, ange en Azure AD e-postadress och välj **Sök**.
1. Markera Azure AD-kontot som returneras och välj sedan **OK**.

Efter konfigureringsstegen ovan kommer fälten **Alias**, **UPN** och **Extern underidentifierare** på fliken **Commerce** på medarbetarens informationssida att fyllas i.

Du måste köra **1060-jobbet (Personal)** i **Retail och Commerce > Retail och Commerce IT > Distributionsschema** för att synkronisera den senaste kassaanvändaren och Azure AD-kontodata till kanalen.

> [!NOTE]
> När medarbetarinformation som exempelvis lösenord, kassabehörighet, associerat Azure AD-konto eller medarbetarens adressbok har uppdaterats i Commerce headquarters rekommenderas det starkt att köra jobbet **1060 (personal)** för att synkronisera den senaste medarbetarinformationen med kanalen. Kassaklienten kan sedan hämta korrekta data för kontroll av användarautentisering och behörighet.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Kassalåsregister och utloggning med Azure AD-autentisering

Följande inträffar när kassan (POS) konfigureras till att använda autentiseringsmetoden för Azure AD:

- Funktionen **Lås register** finns inte i kassaprogrammet (POS). 
- Den **automatiska låsfunktionen** fungerar på samma sätt som den **automatiska utloggningsfunktionen**.
- Om kassaanvändaren väljer **Logga ut** kommer användaren att ombedjas logga in med Azure AD-autentiseringsuppgifter nästa gång kassan (POS) körs, oavsett om enkel inloggning har aktiverats.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Åsidosättningsfunktioner för chef med Azure AD-autentisering

När kassan (POS) har konfigurerats för Azure AD-autentisering öppnar chefsfunktionen för åsidosättning en dialogruta som efterfrågar chefsanvändarens Azure AD-autentiseringsuppgifter. När chefsinloggningen har godkänts tas chefens Azure AD-autentiseringsuppgifter bort och den tidigare användarens Azure AD-autentiseringsuppgifter används för efterföljande kassafunktioner.

> [!NOTE]
> - I Commerce-versionerna 10.0.18 och tidigare har åsidosättningsfunktionen för chefer inte stöd för Azure AD. Ett personals-ID och ett lösenord måste anges även om kassan (POS) har konfigurerats att använda Azure AD-autentiseringsmetoden.
> - När du använder CPOS med webbläsaren Safari på en Apple iOS-enhet måste du först stänga av **Blockera popup-fönster** i Safari-inställningarna för att åsidosättningsfunktionen för chefer ska kunna fungera tillsammans med Azure AD-autentisering. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Metodtips för säkerhet för Azure AD-baserad kassaautentisering på delade enheter

Många återförsäljare konfigurerar sin butiksmiljö på ett sätt som gör att flera användare behöver få åtkomst till kassaprogrammet från en delad fysisk enhet. Även om en enskild inloggning ger en praktisk och sömlös autentiseringsupplevelse kan den här även skapa ett säkerhetskryphål där den aktuella kassaanvändaren kanske inte inser att en annan användares autentiseringsuppgifter används för att utföra transaktioner eller funktioner i kassan (POS). Innan du konfigurerar POS för att använda autentiseringsmetoden för Azure AD bör du granska din säkerhetspolicy och den delade enhetens inloggningsinställningar för att avgöra vilket alternativ som passar bäst.

- Om din butiksmiljö använder ett delat konto (till exempel ett lokalt konto) för inloggning på den fysiska enheten rekommenderas att använda **Azure AD utan alternativet för enkel inloggning**. På så sätt ser du till att varje kassaanvändare explicit anger Azure AD-autentiseringsuppgifter för att logga in i kassan (POS).
- Om din butiksmiljö kräver att medarbetarna använder sina egna Azure AD-konton för att logga in i kassan (POS) och på den fysiska enhet som är kassans värd, rekommenderas du att använda alternativet **Azure AD med enkel inloggning**.

## <a name="additional-resources"></a>Ytterligare resurser

[ Konfigurera en medarbetare](tasks/worker.md)

[Skapa en Retail-funktionsprofil](retail-functionality-profile.md)


[Ställa in utökad inloggningsfunktion för MPOS och Cloud POS](extended-logon.md)

[Metodtips för säkerhet för molnbaserad kassa i delade miljöer](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
