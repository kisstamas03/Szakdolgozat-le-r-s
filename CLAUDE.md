# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Master's thesis (LaTeX document) for the University of Miskolc (Miskolci Egyetem), authored by Kiss Tamás László. The thesis documents the design and implementation of **ME Learning**, a Java/Spring Boot e-learning web application.

The thesis source is in Hungarian. The actual application source code is not present here — only the document.

## Building the Document

Compile with `latexmk` (requires a LaTeX distribution such as MiKTeX or TeX Live):

```bash
latexmk -pdf dolgozat.tex
```

Or compile manually (run twice to resolve references):

```bash
pdflatex dolgozat.tex
bibtex dolgozat
pdflatex dolgozat.tex
pdflatex dolgozat.tex
```

The compiled output is `dolgozat.pdf`.

## Document Structure

- `dolgozat.tex` — root file; inputs all chapters and front matter
- `dolgozat.bib` — BibTeX bibliography
- `chapters/` — the six main thesis chapters (numbered 1–6)
- `cover/` — title page, task description, and declaration pages
- `styles/` — custom `.sty` files for document formatting, Hungarian language support, and code syntax highlighting (C++, Python, Java)
- `images/` — logos and figures

## Chapter Outline

| File | Topic |
|------|-------|
| `chapters/1_introduction.tex` | Bevezetés (Introduction) |
| `chapters/2_concept.tex` | Koncepció (Motivation & requirements) |
| `chapters/3_design.tex` | Tervezés (Architecture & design decisions) |
| `chapters/4_implementation.tex` | Megvalósítás (Implementation details) |
| `chapters/5_test.tex` | Tesztelés (Testing) |
| `chapters/6_summary.tex` | Összefoglalás (Summary & future work) |

## ME Learning Application (described in thesis)

The documented application uses:
- **Backend**: Java 17, Spring Boot 3, Spring Security, Spring Data JPA + Hibernate, Apache POI, Apache PDFBox, JavaMail
- **Frontend**: Thymeleaf, Bootstrap
- **Database**: H2 (dev) / PostgreSQL or MySQL (prod)
- **Roles**: ADMIN, INSTRUCTOR, STUDENT
- **Key features**: course/lesson management, PPT→PDF conversion, quiz system with grading, email notifications, CSRF protection
