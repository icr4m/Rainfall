# Rainfall

> Projet de sécurité — École 42

Rainfall est un challenge CTF sous forme d'ISO qui introduit l'exploitation de binaires ELF sur architecture x86 (i386). L'objectif est de progresser de `level0` à `level9` (+ bonus) en exploitant des vulnérabilités dans des binaires SUID pour récupérer le mot de passe du niveau suivant.

## Concepts abordés

- Buffer overflow (stack & heap)
- Format string (`printf` / `%n`)
- Injection de shellcode
- Reverse engineering / désassemblage GDB
- Hijacking de vtable (C++)
- Exploitation de fonctions non sécurisées (`gets`, `strcpy`, `scanf`…)

## Structure

```
Rainfall/
├── level0/   # Analyse + exploit + source reconstruite
├── level1/
├── ...
├── level9/
├── bonus0/
├── bonus1/
├── bonus2/
└── bonus3/
```

Chaque dossier contient :
- `README.md` — walkthrough de l'exploit
- `source.c` — code C reconstruit depuis le désassemblage

## Environnement

Le projet tourne dans une VM 32 bits fournie par 42 (ISO disponible sur l'intranet) avec les protections désactivées (ASLR off, pas de stack canary, pas de NX).

```bash
# Lancer la VM (QEMU)
./vm_launch.bash

# Se connecter
ssh -p 2222 level0@localhost  # mot de passe : level0
```

## Outils utilisés

`gdb` · `objdump` · `ltrace` · `python2` · `pwntools` · `r2`
