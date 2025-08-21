# Vulnerabilidades de um sistema operacional

### Como construir SO's melhores e mais confiaveis.

<p>Sistemas operacionais confiaveis dao visibilidade sobre o seu _source code_, ou seja, sao de codigo aberto, voce sabe o que o sistema esta fazendo no seu hardware e pode editar conforme a necessidade.
Sistemas de _codigo fechado_ operam de maneira arbitraria e refletem o interesse da sua empresa que colocam seus interesses acima de qualquer optimizacao do sistema. </p>

<p>Os sistemas que se enquadram como confiaveis sao sistemas transparentes que nao escodem seus processos e codigo fonte. Podemos construir um sistema operacional confiavel por meio da comunidade e de empresas que contribuem para o desenvolvimento de projetos. Como grande exemplos temos a Red Hat e Suse que frequentemente aparecem com contribuicoes no codigo do kernel do Linux.</p>

#### [async_pf.h](https://github.com/torvalds/linux/blob/master/virt/kvm/async_pf.h)

````
/* SPDX-License-Identifier: GPL-2.0-only */
/*
 * kvm asynchronous fault support
 *
 * Copyright 2010 Red Hat, Inc.
 *
 * Author:
 *      Gleb Natapov <gleb@redhat.com>
 */
````
<p>Outro exemplo de sistema operacional funcional que se benificia de codigo aberto e freeBSD e variantes, que se usufruem do mesmo sistema de codigo aberto e sao utilizados em grande massa em servidores que exigem um sistema operacional mais robusto.</p>

### Vulnerabilidades que tornam os SOs menos confiavel

<p>Qualquer vulnerabilidade que escala privilegios sao um risco enorme para a confiabilidade de um sistema. Existem inumeros exemplos e sempre aparecem com um alto _score_ quando sao catalogados em CVE (Common Vulnerabilities and Exposures). </p>

Podemos usar como exemplo dois report de vulnerabilidades: <br>
- [nvd.nist.gov](https://nvd.nist.gov/vuln/detail/CVE-2024-6510)
- [Playstation Bounty](https://hackerone.com/reports/2177925)

O segundo sendo uma falha de seguranca que permitiu o escalonamento de privilegios e deu origem ao exploit que permite que Playstations 4 sejam desbloqueados e usados livremente sem a limitacao do fabricante [jailbreak](https://gamesource.pk/jailbreak-ps4-ps5-xbox-nintendo-playstation-gaming-console/) - O sistema operacional dos playstations desde o 4 e um _fork_ de BSD, isso e uma consequencia do licenciamento do que e menos restritivo que o Linux, BSD em geral usam [netbsd](https://www.openbsd.org/policy.html) e Linux usa em geral [Licencas copyleft](https://www.kernel.org/doc/html/next/process/license-rules.html).

<p>O maior exemplo de vulnerabilidade e o jeito que o kernel Linux carrega os drivers no kernel, drivers carregados no kernel tem acesso total ao sistema, tendo a capacidade de sobreescrever firmwares como UEFI e corromper totalmente hardwares. Qualquer software mal intencionado pode ter controle total do sistema e levar a danos permanentes no hardware.<p>

A resposta para esse problema vem da comunidade, nao da comunidade de desenvolvedores do Kernel, mas sim da comunidade de usuarios insatisfeitos, podemos visualizar projetos como [Linux-Libre](https://en.m.wikipedia.org/wiki/Linux-libre), [GUIX](https://guix.gnu.org/pt-BR/) e [PureOS](https://www.pureos.net/).
