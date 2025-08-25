# Workshop-Notes
Detailed notes on workshops attended.
\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage{hyperref}
\usepackage{geometry}
\usepackage{fancyhdr}
\usepackage{titlesec}
\usepackage{xcolor}
\geometry{margin=1in}

% Header & Footer
\pagestyle{fancy}
\fancyhf{}
\rhead{Cybersecurity Notes}
\lhead{Knowledge Collection}
\rfoot{\thepage}

% Title formatting
\titleformat{\section}{\large\bfseries}{\thesection}{0.5em}{}
\titleformat{\subsection}{\normalsize\bfseries}{\thesubsection}{0.5em}{}

% Document Info
\title{\textbf{Knowledge Notes: Cybersecurity, Web Tech \& CTF}}
\author{
    Your Full Name \\[4pt]
    \href{mailto:yourname@gmail.com}{yourname@gmail.com} \\[6pt]
    \href{https://www.linkedin.com/in/yourlinkedin}{linkedin.com/in/yourlinkedin} \\[6pt]
    \href{https://github.com/yourgithub}{github.com/yourgithub}
}
\date{\today}

\begin{document}

\maketitle
\tableofcontents
\newpage

% --------------------------
\section{Ciphers: Encryption \& Decryption}
\subsection{Concept}
\begin{itemize}
    \item Encryption = converting \textbf{plaintext} (readable message) into \textbf{ciphertext} (unreadable form).
    \item Decryption = converting ciphertext back into plaintext using a secret key.
    \item Secure communication requires strong algorithms resistant to brute force or frequency analysis.
\end{itemize}

\subsection{Caesar Cipher}
\begin{itemize}
    \item One of the earliest substitution ciphers.
    \item Each letter is shifted forward or backward by a fixed number (e.g., shift 3: A $\rightarrow$ D).
    \item Very weak by modern standards:
    \begin{itemize}
        \item Only 25 possible shifts.
        \item Easily breakable via brute force or letter frequency analysis.
    \end{itemize}
\end{itemize}

\subsection{Modern View}
\begin{itemize}
    \item Used historically, but now replaced by stronger algorithms like AES, RSA, and ECC.
\end{itemize}

% --------------------------
\section{Steganography}
\subsection{Introduction}
\begin{itemize}
    \item The art of \textbf{concealing information} inside another medium (image, video, text, audio).
    \item Unlike encryption, the goal isn’t to make data unreadable, but to make it invisible.
\end{itemize}

\subsection{Image Steganography}
\begin{itemize}
    \item Example: Hide secret text inside pixels of an image (Least Significant Bit (LSB) encoding).
    \item Looks like a normal image to humans, but tools can extract the hidden payload.
\end{itemize}

\subsection{Difference from Encryption}
\begin{itemize}
    \item Encryption: hides \textbf{content}.
    \item Steganography: hides \textbf{existence}.
    \item They can be combined for layered security.
\end{itemize}

% --------------------------
\section{Web Technology Concepts}
\subsection{Metadata}
\begin{itemize}
    \item “Data about data”.
    \item Provides descriptive information about the properties of the actual content.
    \item Examples:
    \begin{itemize}
        \item Images → EXIF data (camera, GPS coordinates, timestamps).
        \item Web files → title tags, comments, headers.
    \end{itemize}
    \item Useful in forensics, OSINT, and CTFs to retrieve hidden information.
\end{itemize}

\subsection{Web Archives}
\begin{itemize}
    \item Store historical snapshots of websites.
    \item Example: Wayback Machine at archive.org.
    \item Use case: Access websites that are taken down, check older versions for clues, or restore lost content.
\end{itemize}

\subsection{GitHub OSINT}
\begin{itemize}
    \item GitHub accounts often reveal:
    \begin{itemize}
        \item Project files (\texttt{README.md}) containing notes, contact info, or internal hints.
        \item Commit history which may leak credentials or API keys.
        \item Hidden branches with sensitive code.
    \end{itemize}
\end{itemize}

% --------------------------
\section{WASM \& WAT Files}
\begin{itemize}
    \item \textbf{.wasm} – WebAssembly binary file, runs at near-native speed in browsers.
    \item \textbf{.wat} – Text-based human-readable version of a \texttt{.wasm} file.
    \item Often used in CTF challenges:
    \begin{itemize}
        \item Reverse engineer logic from \texttt{.wasm}.
        \item Translate back into C-like pseudo code.
    \end{itemize}
\end{itemize}

% --------------------------
\section{Machine Learning Basics}
\begin{itemize}
    \item Steps to train an ML model:
    \begin{enumerate}
        \item Data collection.
        \item Data preprocessing (cleaning, normalization).
        \item Choose model type (Regression, Classification, Neural Networks).
        \item Train model on dataset.
        \item Evaluate performance (accuracy, precision, recall).
        \item Deploy model for real-world use.
    \end{enumerate}
    \item Applied in security: anomaly detection, malware classification, phishing detection.
\end{itemize}

% --------------------------
\section{CTF Notes \& Investigation Tips}
\begin{itemize}
    \item Always check code for \textbf{hidden comments}.
    \item Use \texttt{Ctrl + Shift + I} in browser to inspect elements.
    \item Look inside:
    \begin{itemize}
        \item HTML \textbf{title tag} (sometimes contains hints).
        \item Source code comments.
        \item Network tab: inspect response headers or hidden API data.
        \item Metadata in files (images, PDFs, Word documents).
        \item GitHub repository commits, branches.
        \item \texttt{.wasm/.wat} files for hidden logic.
    \end{itemize}
    \item “Think like a puzzle solver” – every unintended file/field could be a clue.
\end{itemize}

% --------------------------
\section{Miscellaneous Notes}
\begin{itemize}
    \item DBWhatsApp – exploration of WhatsApp database files often used in forensics.
    \item README.md – crucial starting point for GitHub repos, contains summaries of purpose.
    \item Network responses – check JSON/XML for leftover debug fields.
\end{itemize}

\end{document}
