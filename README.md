# <ins>Trust_zone_ARM </ins>

Renseignement à propos des Trust zone sur les ARM

**Sources**

``site officiel`` [armDeveloper](https://developer.arm.com/ip-products/security-ip/trustzone)

``Article`` [About trustZone](https://www.microcontrollertips.com/embedded-security-brief-arm-trustzone-explained/)

``Video`` [ARM TrustZone for dummies](https://www.youtube.com/watch?v=ecBByjwny3s)

## About trustZone

Arm TrustZone est une technologie de sécurité qui commence dans le matériel de la puce du processeur Arm, qui est la base du **démarrage sécurisé**.

Arm TrustZone is an embedded security technology that **starts at the hardware level** by creating two environments that can run simultaneously on a single core: a **secure world** and a **not-as-secure world** (non-secure world)

>isolation hardware qui permet de faire tourner un Linux d'un coté et un OS minimal, spécialisé dans la sécurité qui va faire tourner des applications de sécurité (verification et update de firmware, signature, chiffrement, alertes ...)

TrustZone is based on the principle of **least privilege**, which means that system modules like drivers and applications do not have access to a resource unless necessary.

> **Rappel du principe de ``last privilege``**:
Service et éxécutable doivent être configurés et intégrés adin d'accorder le strict nécessaire en privilège .
>> **Les conséquences sont donc limitées aux privilèges octroyés.**

TrustZone includes a **Secure Boot Sequence** verifies secure boot images. Images can be cryptographically authenticated using public and private keys. Once the system has finished booting up, the two OSes can communicate via a monitor kernel mode, which behaves much like a context switch.

Aussi pour ARM, il faut bien distinguer:
* Cortex-A  Micro-Processeur
*	Cortex-M Micro-Controler
*	Cortex-R RealTime

On retrouve les "-A" "-M" dans beaucoup de denominations, par exemple Trusted Firmware-M (TF-M)  vs.  TF-A pour les Cortex-A.
