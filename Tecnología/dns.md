---
title: "DNS"
author: "Glazzier"
date: "2025-03-21"
---

# DNS (Domain Name System)

El **Sistema de Nombres de Dominio (DNS, por sus siglas en inglés)** es un protocolo fundamental en Internet que traduce los **nombres de dominio** legibles por humanos (como *www.ejemplo.com*) en **direcciones IP** numéricas que identifican dispositivos en una red. Gracias al DNS, los usuarios pueden acceder a sitios web sin necesidad de recordar direcciones IP complejas.

## Historia

El concepto de asignar nombres a direcciones en una red comenzó antes del DNS, con un archivo llamado **HOSTS.TXT**, mantenido por el **Stanford Research Institute (SRI)** en los años 70. A medida que ARPANET (precursor de Internet) crecía, este sistema manual se volvió insostenible.

En **1983**, **Paul Mockapetris** diseñó el DNS para mejorar la escalabilidad de la red. Su implementación permitió la distribución de la resolución de nombres en servidores jerárquicos, eliminando la necesidad de un único archivo centralizado.

El sistema fue formalizado en los documentos **RFC 882 y 883**, reemplazados posteriormente por **RFC 1034 y 1035**, que siguen siendo la base del DNS moderno.

## Funcionamiento del DNS

El DNS opera mediante una arquitectura distribuida y jerárquica. Su función principal es la **resolución de nombres**, que se lleva a cabo en varios pasos:

1. **Consulta del usuario:** Cuando un usuario ingresa un dominio en su navegador, su dispositivo solicita la dirección IP al servidor DNS configurado.
2. **Búsqueda en caché:** Si la dirección ya fue consultada recientemente, el sistema puede devolverla desde la memoria caché sin necesidad de consultar servidores externos.
3. **Consulta a servidores raíz:** Si la dirección no está en caché, el servidor DNS contacta a los **servidores raíz** (Root Servers), que redirigen la consulta al servidor TLD (Top-Level Domain) correspondiente.
4. **Consulta al servidor TLD:** Este servidor proporciona la dirección del **servidor autoritativo** para el dominio en cuestión.
5. **Resolución final:** El servidor autoritativo devuelve la dirección IP del dominio, permitiendo la conexión al sitio web.

## Jerarquía del DNS

El DNS está organizado en una estructura jerárquica con diferentes niveles:

- **Servidores raíz:** Son la capa superior del DNS y dirigen las consultas a los servidores de dominio de nivel superior (TLD). Existen 13 servidores raíz en el mundo.
- **Servidores TLD (Top-Level Domain):** Gestionan los dominios de primer nivel como **.com, .org, .net, .es, .gov**.
- **Servidores autoritativos:** Contienen la información específica de cada dominio y responden con la dirección IP correspondiente.

## Tipos de Registros DNS

Los registros DNS almacenan información sobre los dominios y direcciones IP. Algunos de los más comunes son:

- **A (Address):** Asigna un dominio a una dirección IPv4.
- **AAAA:** Similar al registro A, pero para direcciones IPv6.
- **CNAME (Canonical Name):** Redirige un dominio a otro nombre de dominio.
- **MX (Mail Exchange):** Especifica los servidores de correo para un dominio.
- **TXT:** Contiene información arbitraria, utilizada para verificaciones de seguridad como SPF y DKIM.
- **NS (Name Server):** Indica los servidores de nombres responsables de un dominio.

## Importancia del DNS

El DNS es clave para el funcionamiento de Internet, ya que:

- Facilita la navegación sin necesidad de recordar direcciones IP.
- Optimiza la carga de páginas gracias a la **caché DNS**.
- Es fundamental para servicios como el correo electrónico y la seguridad en línea.

## Problemas y Vulnerabilidades

El DNS, aunque esencial, presenta riesgos de seguridad:

- **Ataques de envenenamiento de caché (DNS Spoofing):** Un atacante introduce direcciones IP falsas en cachés DNS, redirigiendo usuarios a sitios maliciosos.
- **DDoS en servidores DNS:** Grandes volúmenes de tráfico pueden colapsar servidores DNS, dejando inaccesibles múltiples servicios.
- **Secuestro de DNS:** Un atacante modifica la configuración de un dominio para redirigir tráfico a servidores no autorizados.

Para mitigar estos riesgos, se implementan medidas como **DNSSEC (Domain Name System Security Extensions)**, que protege la integridad y autenticidad de las respuestas DNS mediante criptografía.