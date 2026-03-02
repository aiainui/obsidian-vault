---
title: "Snapshot"
zotero_key: VKNGWYGB
url: https://docs.langchain.com/oss/python/deepagents/overview
exported: 2026-03-03 01:29:19
---

Deep Agents overview - Docs by LangChain

::: {.sf-hidden hidden=""}
:::

::: {.relative .antialiased .text-gray-500 .dark:text-gray-400}
[Skip to main content](#content-area){.sr-only .focus:not-sr-only .focus:fixed .focus:top-2 .focus:left-2 .focus:z-50 .focus:p-2 .focus:text-sm .focus:bg-background-light .dark:focus:bg-background-dark .focus:rounded-md .focus:outline-primary .dark:focus:outline-primary-light}

::: {#navbar .z-30 .fixed .lg:sticky .top-0 .w-full .peer .is-not-custom .is-not-center .is-not-wide .is-not-frame}
::: {.z-10 .absolute .w-full .h-full .border-b .border-gray-100 .dark:border-gray-800}
:::

::: {.z-0 .absolute .inset-0 .bg-background-light .dark:bg-background-dark}
:::

::: {#banner .px-2 .w-full .text-white/90 .dark:text-white/90 .max-h-16 .md:h-10 .relative .text-center .items-center .justify-center .text-sm .line-clamp-2 .md:truncate .md:[&>*]:truncate .bg-primary-dark .font-medium .z-[45]}
::: {.space-y-4 .whitespace-normal .my-2 .md:[&>p]:m-0 .prose .prose-sm .prose-dark .dark:prose-invert .text-white/90 .dark:text-white/90}
🚀 [Share how you\'re building agents](https://bit.ly/agent-engineering-survey){.wrap-anywhere .font-medium .text-primary .underline} for a chance to win LangChain swag!
:::
:::

::: {.z-10 .mx-auto .relative .max-w-8xl .px-0 .lg:px-5}
::: {.relative}
::: {.flex .items-center .lg:px-4 .h-14 .min-w-0 .mx-4 .lg:mx-0}
::: {.h-full .relative .flex-1 .flex .items-center .gap-x-4 .min-w-0}
::: {.flex-1 .flex .items-center .gap-x-4}
[[Docs by LangChain home page]{.sr-only}![light logo](data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNjUiIGhlaWdodD0iMzIiIHZpZXdCb3g9IjAgMCAyNjUgMzIiIGZpbGw9Im5vbmUiPgo8cGF0aCBkPSJNNDkuNzM5NyA5LjQ5OTg3QzUwLjk2MDcgMTAuNzIwMiA1MC45NjA3IDEyLjcwNjEgNDkuNzM5NyAxMy45MjY0TDQ3LjAwNDUgMTYuNjE1OUw0Ni45NzY3IDE2LjQ2MThDNDYuNzc3IDE1LjM1NjQgNDYuMjUxMiAxNC4zNTM0IDQ1LjQ1NzQgMTMuNTYwMUM0NC44NTk2IDEyLjk2MzggNDQuMTUzIDEyLjUyMjkgNDMuMzU2NyAxMi4yNUM0Mi44NjI1IDEyLjc0NjUgNDIuNTkwNyAxMy4zOTcxIDQyLjU5MDcgMTQuMDgxOEM0Mi41OTA3IDE0LjIyMDcgNDIuNjAzNCAxNC4zNjQ4IDQyLjYyODcgMTQuNTA4OEM0My4wNjcyIDE0LjY2NjcgNDMuNDU1MyAxNC45MTA1IDQzLjc4MTQgMTUuMjM2NEM0NS4wMDI0IDE2LjQ1NjggNDUuMDAyNCAxOC40NDI2IDQzLjc4MTQgMTkuNjYzTDQxLjQwMDEgMjIuMDQzQzQwLjc4OTYgMjIuNjUzMSAzOS45ODgyIDIyLjk1NzYgMzkuMTg1NiAyMi45NTc2QzM4LjM4MyAyMi45NTc2IDM3LjU4MTYgMjIuNjUzMSAzNi45NzExIDIyLjA0M0MzNS43NTAxIDIwLjgyMjcgMzUuNzUwMSAxOC44MzY4IDM2Ljk3MTEgMTcuNjE2NEwzOS43MDY0IDE0LjkyODJMMzkuNzM0MiAxNS4wODIzQzM5LjkzMjYgMTYuMTg1MSA0MC40NTg0IDE3LjE4ODIgNDEuMjU0NyAxNy45ODI4QzQxLjg1MzggMTguNTgxNiA0Mi41MTc0IDE4Ljk3OTUgNDMuMzEyNSAxOS4yNTExTDQzLjQ1OTEgMTkuMTA0NkM0My45MDQgMTguNjU5OSA0NC4xNDc5IDE4LjA2ODcgNDQuMTQ3OSAxNy40MzgzQzQ0LjE0NzkgMTcuMjk4MSA0NC4xMzUzIDE3LjE1NzkgNDQuMTExMyAxNy4wMjAyQzQzLjY1MjUgMTYuODY4NiA0My4yNzQ1IDE2LjY1MjYgNDIuOTMwNyAxNi4zMDlDNDIuNDM1MyAxNS44MTM3IDQyLjEyNjkgMTUuMTgwOCA0Mi4wNDA5IDE0LjQ3OTdDNDIuMDM0NiAxNC40MjkyIDQyLjAzMDggMTQuMzc5OSA0Mi4wMjU3IDE0LjMyOTRDNDEuOTU3NSAxMy40MTYgNDIuMjg3NCAxMi41MjQyIDQyLjkzMDcgMTEuODgyNEw0NS4zMTIxIDkuNTAyMzlDNDUuOTAyMyA4LjkxMjQ0IDQ2LjY4ODUgOC41ODY1MiA0Ny41MjY1IDguNTg2NTJDNDguMzY0NSA4LjU4NjUyIDQ5LjE1MDcgOC45MTExOCA0OS43NDEgOS41MDIzOUw0OS43Mzk3IDkuNDk5ODdaTTYyLjE3NDcgMTUuNzkxQzYyLjE3NDcgMjQuNDk4OCA1NS4wODYzIDMxLjU4MiA0Ni4zNzUxIDMxLjU4MkgxNS43OTk2QzcuMDg4MzQgMzEuNTgyIDAgMjQuNDk4OCAwIDE1Ljc5MUMwIDcuMDgzMjEgNy4wODgzNCAwIDE1Ljc5OTYgMEg0Ni4zNzUxQzU1LjA4NzYgMCA2Mi4xNzQ3IDcuMDg0NDggNjIuMTc0NyAxNS43OTFaTTMwLjQ0OSAyMy43MTA1QzMwLjY5OCAyMy40MDg2IDI5LjU0NzggMjIuNTU4NCAyOS4zMTI3IDIyLjI0NjRDMjguODM0OSAyMS43Mjg0IDI4LjgzMjQgMjAuOTgzMSAyOC41MTAxIDIwLjM3OEMyNy43MjE0IDE4LjU1MTMgMjYuODE1MSAxNi43Mzg1IDI1LjU0NzQgMTUuMTkyMkMyNC4yMDc2IDEzLjUwMDcgMjIuNTU0MyAxMi4xMDEgMjEuMTAyIDEwLjUxM0MyMC4wMjM4IDkuNDA1MTIgMTkuNzM1NiA3LjgyNzI4IDE4Ljc4MzkgNi42MzYwMUMxNy40NzE5IDQuNjk5NCAxMy4zMjM1IDQuMTcxMzUgMTIuNzE1NSA2LjkwNjM1QzEyLjcxODEgNi45OTIyNiAxMi42OTE1IDcuMDQ2NTggMTIuNjE2OSA3LjEwMDlDMTIuMjgwNyA3LjM0NDcxIDExLjk4MTIgNy42MjM5IDExLjcyOTYgNy45NjExOUMxMS4xMTQxIDguODE3NyAxMS4wMTkzIDEwLjI3MDUgMTEuNzg3OCAxMS4wMzk4QzExLjgxMzEgMTAuNjM0MyAxMS44MjcgMTAuMjUxNSAxMi4xNDggOS45NjA5N0MxMi43NDIxIDEwLjQ3MDEgMTMuNjM5NSAxMC42NTA3IDE0LjMyODQgMTAuMjcwNUMxNS44NTAyIDEyLjQ0MiAxNS40NzEgMTUuNDQ2MSAxNi42NzkzIDE3Ljc4NTdDMTcuMDEzIDE4LjMzOSAxNy4zNDkzIDE4LjkwMzcgMTcuNzc3NyAxOS4zODg4QzE4LjEyNTMgMTkuOTI5NSAxOS4zMjYxIDIwLjU2NzUgMTkuMzk2OSAyMS4wNjc3QzE5LjQwOTUgMjEuOTI2OCAxOS4zMDg0IDIyLjg2NTQgMTkuODcyMSAyMy41ODQyQzIwLjEzNzYgMjQuMTIyMyAxOS40ODU0IDI0LjY2MyAxOC45NTk1IDI0LjU5NjFDMTguMjc3IDI0LjY4OTYgMTcuNDQ0IDI0LjEzNzUgMTYuODQ2MiAyNC40NzczQzE2LjYzNTEgMjQuNzA2IDE2LjIyMTggMjQuNDUzMyAxNi4wMzk4IDI0Ljc3MDRDMTUuOTc2NiAyNC45MzQ2IDE1LjYzNTMgMjUuMTY1OCAxNS44Mzg4IDI1LjMyMzdDMTYuMDY1MSAyNS4xNTE5IDE2LjI3NDkgMjQuOTcyNSAxNi41Nzk1IDI1LjA3NDlDMTYuNTM0IDI1LjMyMjUgMTYuNzI5OSAyNS4zNTc4IDE2Ljg4NTQgMjUuNDI5OEMxNi44ODAzIDI1LjU5NzkgMTYuNzgxNyAyNS43Njk3IDE2LjkxMDcgMjUuOTEyNEMxNy4wNjExIDI1Ljc2MDggMTcuMTUwOCAyNS41NDYxIDE3LjM4OTcgMjUuNDgyOUMxOC4xODM1IDI2LjU0MDMgMTguOTkxMSAyNC40MTI5IDIwLjcwODkgMjUuMzcwNUMyMC4zNiAyNS4zNTI4IDIwLjA1MDQgMjUuMzk3IDE5LjgxNTMgMjUuNjgzOEMxOS43NTcxIDI1Ljc0ODIgMTkuNzA3OCAyNS44MjQgMTkuODEwMiAyNS45MDc0QzIwLjczNjcgMjUuMzA5OCAyMC43MzE2IDI2LjExMiAyMS4zMzMzIDI1Ljg2NTdDMjEuNzk1OSAyNS42MjQ0IDIyLjI1NiAyNS4zMjI1IDIyLjgwNTggMjUuNDA4NEMyMi4yNzEyIDI1LjU2MjUgMjIuMjQ5NyAyNS45OTIgMjEuOTM2MiAyNi4zNTQ2QzIxLjg4MzEgMjYuNDEwMSAyMS44NTc4IDI2LjQ3MzMgMjEuOTE5OCAyNi41NjU1QzIzLjAyOTUgMjYuNDcyIDIzLjEyMDUgMjYuMTAzMiAyNC4wMTY3IDI1LjY1MDlDMjQuNjg1MyAyNS4yNDI5IDI1LjM1MTQgMjYuMjMyIDI1LjkzMDMgMjUuNjY4NkMyNi4wNTggMjUuNTQ2MSAyNi4yMzI0IDI1LjU4NzcgMjYuMzkwNCAyNS41NzEzQzI2LjE4ODIgMjQuNDkzNyAyMy45NjQ5IDI1Ljc2ODQgMjQuMDAwMyAyNC4zMjMyQzI0LjcxNTcgMjMuODM2OCAyNC41NTE0IDIyLjkwNTggMjQuNTk5NCAyMi4xNTQxQzI1LjQyMjIgMjIuNjEwMiAyNi4zMzczIDIyLjg3NTUgMjcuMTQzOCAyMy4zMTEzQzI3LjU1MDggMjMuOTY4MiAyOC4xODkxIDI0LjgzNjEgMjkuMDM5NyAyNC43NzkyQzI5LjA2MjUgMjQuNzEzNiAyOS4wODI3IDI0LjY1NTQgMjkuMTA2NyAyNC41ODg1QzI5LjM2NDYgMjQuNjMyNyAyOS42OTU3IDI0LjgwMzIgMjkuODM3MyAyNC40NzczQzMwLjIyMjggMjQuODgwMyAzMC43ODkgMjQuODYwMSAzMS4yOTM0IDI0Ljc1NjVDMzEuNjY2MiAyNC40NTMzIDMwLjU5MTkgMjQuMDIxMyAzMC40NDc4IDIzLjcwOTJMMzAuNDQ5IDIzLjcxMDVaTTUzLjAyNDggMTEuNzEzMUM1My4wMjQ4IDEwLjI0MjcgNTIuNDUzNSA4Ljg2MTkxIDUxLjQxNTggNy44MjQ3NkM1MC4zNzgxIDYuNzg3NjEgNDguOTk2NSA2LjIxNjYgNDcuNTI0IDYuMjE2NkM0Ni4wNTE1IDYuMjE2NiA0NC42NyA2Ljc4NzYxIDQzLjYzMjIgNy44MjQ3Nkw0MS4yNTA5IDEwLjIwNDhDNDAuNjk0OCAxMC43NjA2IDQwLjI3MjYgMTEuNDEzNyAzOS45OTU4IDEyLjE0NTJMMzkuOTc5NCAxMi4xODY5TDM5LjkzNjQgMTIuMTk5NUMzOS4wNzE4IDEyLjQ2NjEgMzguMzA5NyAxMi45MjM0IDM3LjY3MTQgMTMuNTYxM0wzNS4yOSAxNS45NDEzQzMzLjE0NTEgMTguMDg2NCAzMy4xNDUxIDIxLjU3NTYgMzUuMjkgMjMuNzE5NEMzNi4zMjc4IDI0Ljc1NjUgMzcuNzA5MyAyNS4zMjc1IDM5LjE4MDUgMjUuMzI3NUM0MC42NTE4IDI1LjMyNzUgNDIuMDM0NiAyNC43NTY1IDQzLjA3MjMgMjMuNzE5NEw0NS40NTM2IDIxLjMzOTNDNDYuMDA3MiAyMC43ODYgNDYuNDI2OSAyMC4xMzU0IDQ2LjcwMzcgMTkuNDA1M0w0Ni43MjAxIDE5LjM2MzZMNDYuNzYzMSAxOS4zNDk3QzQ3LjYxMjUgMTkuMDg5NCA0OC4zOTYxIDE4LjYxNyA0OS4wMzE5IDE3Ljk4MjhMNTEuNDEzMiAxNS42MDI4QzUyLjQ1MSAxNC41NjU2IDUzLjAyMjMgMTMuMTg0OSA1My4wMjIzIDExLjcxMzFINTMuMDI0OFpNMjEuNzg4MyAyMS45MzA1QzIxLjU4MzYgMjIuNzI4OSAyMS41MTY2IDI0LjA4OTUgMjAuNDc3NiAyNC4xMjg3QzIwLjM5MTYgMjQuNTg5OCAyMC43OTc0IDI0Ljc2MjggMjEuMTY1MiAyNC42MTVDMjEuNTMwNSAyNC40NDcgMjEuNzAzNiAyNC43NDc3IDIxLjgyNjIgMjUuMDQ3MUMyMi4zOSAyNS4xMjkyIDIzLjIyNDIgMjQuODU4OCAyMy4yNTU4IDI0LjE5MThDMjIuNDE0IDIzLjcwNjcgMjIuMTUzNiAyMi43ODQ1IDIxLjc4NzEgMjEuOTMwNUgyMS43ODgzWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMjU5LjM4MSAyNi40Nzk3QzI1Ny43MjUgMjYuNDc5NyAyNTYuMzUgMjYuMTM2NCAyNTUuMjU1IDI1LjQ0OTdDMjU0LjE2IDI0Ljc1NDEgMjUzLjQ4MSAyMy43OTY0IDI1My4yMTkgMjIuNTc2N0wyNTQuMzg2IDIyLjM1OTlDMjU0LjYzIDIzLjI2MzQgMjU1LjIgMjMuOTg2MSAyNTYuMDk2IDI0LjUyODJDMjU3LjAwMSAyNS4wNzAzIDI1OC4xMDUgMjUuMzQxMyAyNTkuNDA4IDI1LjM0MTNDMjYwLjczOCAyNS4zNDEzIDI2MS43OTIgMjUuMDU2NyAyNjIuNTcgMjQuNDg3NkMyNjMuMzU4IDIzLjkxODQgMjYzLjc1MSAyMy4xNDU5IDI2My43NTEgMjIuMTcwMkMyNjMuNzUxIDIxLjYzNzEgMjYzLjYzNCAyMS4yMDM1IDI2My4zOTggMjAuODY5MkMyNjMuMTYzIDIwLjUyNTkgMjYyLjcwMiAyMC4yMTQyIDI2Mi4wMTQgMTkuOTM0MUMyNjEuMzM1IDE5LjY1NCAyNjAuMzMxIDE5LjMzMzMgMjU5LjAwMSAxOC45NzE5QzI1Ny42MDcgMTguNTkyNSAyNTYuNTIxIDE4LjIyNjYgMjU1Ljc0MyAxNy44NzQyQzI1NC45NzQgMTcuNTEyOCAyNTQuNDMxIDE3LjExMDggMjU0LjExNSAxNi42NjgxQzI1My44MDcgMTYuMjE2NCAyNTMuNjUzIDE1LjY2NTMgMjUzLjY1MyAxNS4wMTQ4QzI1My42NTMgMTQuMjM3OCAyNTMuODg0IDEzLjU1MTIgMjU0LjM0NSAxMi45NTQ5QzI1NC44MDcgMTIuMzU4NiAyNTUuNDQ1IDExLjg5MzMgMjU2LjI1OSAxMS41NTlDMjU3LjA3MyAxMS4yMjQ4IDI1OC4wMTQgMTEuMDU3NiAyNTkuMDgyIDExLjA1NzZDMjYwLjE1OSAxMS4wNTc2IDI2MS4xMjcgMTEuMjM4MyAyNjEuOTg3IDExLjU5OTdDMjYyLjg1NSAxMS45NTIgMjYzLjU1MiAxMi40NDg5IDI2NC4wNzcgMTMuMDkwNEMyNjQuNjExIDEzLjcyMjggMjY0LjkxOCAxNC40NTQ2IDI2NSAxNS4yODU4TDI2My44MzMgMTUuNTAyNkMyNjMuNjYxIDE0LjQ4MTcgMjYzLjEzNiAxMy42Nzc3IDI2Mi4yNTggMTMuMDkwNEMyNjEuMzkgMTIuNDk0MSAyNjAuMzA0IDEyLjE5NiAyNTkuMDAxIDEyLjE5NkMyNTcuNzc5IDEyLjE3NzkgMjU2Ljc3OSAxMi40MjY0IDI1Ni4wMDEgMTIuOTQxM0MyNTUuMjMyIDEzLjQ1NjMgMjU0Ljg0NyAxNC4xMjk0IDI1NC44NDcgMTQuOTYwNkMyNTQuODQ3IDE1LjQyMTMgMjU0Ljk3OSAxNS44MTg5IDI1NS4yNDEgMTYuMTUzMUMyNTUuNTAzIDE2LjQ3ODQgMjU1Ljk2IDE2Ljc3NjUgMjU2LjYxMiAxNy4wNDc2QzI1Ny4yNjMgMTcuMzE4NiAyNTguMTY4IDE3LjU5ODcgMjU5LjMyNiAxNy44ODc4QzI2MC43OTIgMTguMjU4MiAyNjEuOTMyIDE4LjYzMzEgMjYyLjc0NyAxOS4wMTI2QzI2My41NyAxOS4zOTIgMjY0LjE0NSAxOS44MzQ3IDI2NC40NzEgMjAuMzQwN0MyNjQuODA1IDIwLjg0NjYgMjY0Ljk3MyAyMS40NzQ1IDI2NC45NzMgMjIuMjI0NEMyNjQuOTczIDIzLjU1MjUgMjY0LjQ3NSAyNC41OTYgMjYzLjQ4IDI1LjM1NDlDMjYyLjQ4NCAyNi4xMDQ3IDI2MS4xMTggMjYuNDc5NyAyNTkuMzgxIDI2LjQ3OTdaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yNDUuMjkxIDI2LjUwNjhDMjQzLjgzNCAyNi41MDY4IDI0Mi42MTMgMjYuMTgxNSAyNDEuNjI2IDI1LjUzMUMyNDAuNjQgMjQuODgwNiAyMzkuODkzIDIzLjk3NzEgMjM5LjM4NyAyMi44MjA3QzIzOC44OCAyMS42NTUyIDIzOC42MTMgMjAuMzA5IDIzOC41ODYgMTguNzgyMkMyMzguNjEzIDE3LjIxOTIgMjM4Ljg4IDE1Ljg1OTUgMjM5LjM4NyAxNC43MDMxQzIzOS45MDIgMTMuNTQ2NiAyNDAuNjU0IDEyLjY1MjIgMjQxLjY0IDEyLjAxOThDMjQyLjYyNiAxMS4zNzgzIDI0My44NDMgMTEuMDU3NiAyNDUuMjkxIDExLjA1NzZDMjQ2LjY0OCAxMS4wNTc2IDI0Ny44NTYgMTEuMzgyOSAyNDguOTE1IDEyLjAzMzRDMjQ5Ljk4MyAxMi42NzQ4IDI1MC43MzggMTMuNTYwMiAyNTEuMTgxIDE0LjY4OTVMMjUwLjA5NiAxNS4xNTAzQzI0OS42ODggMTQuMjEwNyAyNDkuMDYgMTMuNDgzNCAyNDguMjA5IDEyLjk2ODRDMjQ3LjM2OCAxMi40NTM1IDI0Ni4zOTUgMTIuMTk2IDI0NS4yOTEgMTIuMTk2QzI0NC4wNiAxMi4xOTYgMjQzLjA0MiAxMi40NzYgMjQyLjIzNyAxMy4wMzYyQzI0MS40MzIgMTMuNTg3MyAyNDAuODMgMTQuMzU5OCAyNDAuNDMyIDE1LjM1MzZDMjQwLjAzNCAxNi4zMzgzIDIzOS44MjYgMTcuNDgxMiAyMzkuODA3IDE4Ljc4MjJDMjM5LjgzNSAyMC43Njk4IDI0MC4zMDUgMjIuMzY0NCAyNDEuMjE5IDIzLjU2NkMyNDIuMTMzIDI0Ljc2NzYgMjQzLjQ5IDI1LjM2ODQgMjQ1LjI5MSAyNS4zNjg0QzI0Ni4zNjggMjUuMzY4NCAyNDcuMzIyIDI1LjEyIDI0OC4xNTUgMjQuNjIzMUMyNDguOTg3IDI0LjEyNjIgMjQ5LjYyNSAyMy4zOTg5IDI1MC4wNjggMjIuNDQxMkwyNTEuMTgxIDIyLjkyOTFDMjUwLjU3NSAyNC4xMDM2IDI0OS43NzQgMjQuOTkzNSAyNDguNzc5IDI1LjU5ODhDMjQ3Ljc4NCAyNi4yMDQxIDI0Ni42MjEgMjYuNTA2OCAyNDUuMjkxIDI2LjUwNjhaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yMjkuNzAzIDI2LjUwNjhDMjI4LjI1NSAyNi41MDY4IDIyNy4wMzQgMjYuMTc3IDIyNi4wMzggMjUuNTE3NUMyMjUuMDQzIDI0Ljg1OCAyMjQuMjg3IDIzLjk0NTUgMjIzLjc3MiAyMi43OEMyMjMuMjU2IDIxLjYxNDUgMjIyLjk5OCAyMC4yNzI5IDIyMi45OTggMTguNzU1MUMyMjIuOTk4IDE3LjIxOTIgMjIzLjI2IDE1Ljg3MzEgMjIzLjc4NSAxNC43MTY2QzIyNC4zMSAxMy41NjAyIDIyNS4wNyAxMi42NjEzIDIyNi4wNjUgMTIuMDE5OEMyMjcuMDcgMTEuMzc4MyAyMjguMjgyIDExLjA1NzYgMjI5LjcwMyAxMS4wNTc2QzIzMS4xNiAxMS4wNTc2IDIzMi4zODYgMTEuMzg3NCAyMzMuMzgxIDEyLjA0NjlDMjM0LjM3NyAxMi42OTc0IDIzNS4xMjggMTMuNjAwOSAyMzUuNjM0IDE0Ljc1NzNDMjM2LjE1IDE1LjkxMzcgMjM2LjQwOCAxNy4yNDYzIDIzNi40MDggMTguNzU1MUMyMzYuNDA4IDIwLjMgMjM2LjE1IDIxLjY1NTIgMjM1LjYzNCAyMi44MjA3QzIzNS4xMTkgMjMuOTc3MSAyMzQuMzU4IDI0Ljg4MDYgMjMzLjM1NCAyNS41MzFDMjMyLjM1OSAyNi4xODE1IDIzMS4xNDIgMjYuNTA2OCAyMjkuNzAzIDI2LjUwNjhaTTIyOS43MDMgMjUuMzY4NEMyMzEuNTQ5IDI1LjM2ODQgMjMyLjkyNCAyNC43NTg2IDIzMy44MjkgMjMuNTM4OUMyMzQuNzM0IDIyLjMxMDIgMjM1LjE4NiAyMC43MTU2IDIzNS4xODYgMTguNzU1MUMyMzUuMTg2IDE2Ljc1ODUgMjM0LjcyOSAxNS4xNjg0IDIzMy44MTYgMTMuOTg0OEMyMzIuOTExIDEyLjc5MjMgMjMxLjU0IDEyLjE5NiAyMjkuNzAzIDEyLjE5NkMyMjguNDYzIDEyLjE5NiAyMjcuNDM2IDEyLjQ3NiAyMjYuNjIyIDEzLjAzNjJDMjI1LjgxNyAxMy41OTYzIDIyNS4yMTUgMTQuMzY4OCAyMjQuODE3IDE1LjM1MzZDMjI0LjQxOSAxNi4zMzgzIDIyNC4yMiAxNy40NzIyIDIyNC4yMiAxOC43NTUxQzIyNC4yMiAyMC43NDI3IDIyNC42ODEgMjIuMzQxOCAyMjUuNjA0IDIzLjU1MjVDMjI2LjUzNiAyNC43NjMxIDIyNy45MDIgMjUuMzY4NCAyMjkuNzAzIDI1LjM2ODRaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yMDYuMTA0IDI2LjEwMDJWNi41ODU0NUgyMTEuODMyQzIxMi4wNjcgNi41ODU0NSAyMTIuNDQzIDYuNTg5OTcgMjEyLjk1OSA2LjU5OUMyMTMuNDc1IDYuNjA4MDQgMjEzLjk2OCA2LjY0ODY5IDIxNC40MzggNi43MjA5N0MyMTUuODc3IDYuOTI4NzYgMjE3LjA2NyA3LjQ3OTg3IDIxOC4wMDggOC4zNzQzQzIxOC45NTggOS4yNjg3MiAyMTkuNjY0IDEwLjQwNzEgMjIwLjEyNSAxMS43ODk0QzIyMC41ODcgMTMuMTYyNiAyMjAuODE3IDE0LjY4MDUgMjIwLjgxNyAxNi4zNDI4QzIyMC44MTcgMTguMDE0MiAyMjAuNTg3IDE5LjU0MTEgMjIwLjEyNSAyMC45MjM0QzIxOS42NjQgMjIuMjk2NiAyMTguOTU4IDIzLjQzMDUgMjE4LjAwOCAyNC4zMjQ5QzIxNy4wNjcgMjUuMjEwMyAyMTUuODc3IDI1Ljc1NjkgMjE0LjQzOCAyNS45NjQ3QzIxMy45NzcgMjYuMDI3OSAyMTMuNDc5IDI2LjA2ODYgMjEyLjk0NSAyNi4wODY2QzIxMi40MiAyNi4wOTU3IDIxMi4wNDkgMjYuMTAwMiAyMTEuODMyIDI2LjEwMDJIMjA2LjEwNFpNMjA3LjMyNiAyNC45NjE4SDIxMS44MzJDMjEyLjI2NyAyNC45NjE4IDIxMi43MDEgMjQuOTQ4MyAyMTMuMTM1IDI0LjkyMTJDMjEzLjU3OSAyNC44OTQxIDIxMy45NSAyNC44NTM0IDIxNC4yNDggMjQuNzk5MkMyMTUuNTMzIDI0LjU4MjQgMjE2LjU2NSAyNC4wOSAyMTcuMzQzIDIzLjMyMkMyMTguMTMgMjIuNTQ1MSAyMTguNyAyMS41NjAzIDIxOS4wNTMgMjAuMzY3N0MyMTkuNDE1IDE5LjE2NjEgMjE5LjU5NiAxNy44MjQ1IDIxOS41OTYgMTYuMzQyOEMyMTkuNTk2IDE0Ljg2MTEgMjE5LjQxNSAxMy41MjQgMjE5LjA1MyAxMi4zMzE1QzIxOC43IDExLjEyOTkgMjE4LjEzIDEwLjE0NTEgMjE3LjM0MyA5LjM3NzE0QzIxNi41NjUgOC42MDAxNiAyMTUuNTMzIDguMTAzMjYgMjE0LjI0OCA3Ljg4NjQzQzIxMy45NSA3LjgzMjIyIDIxMy41NzQgNy43OTE1NyAyMTMuMTIyIDcuNzY0NDZDMjEyLjY2OSA3LjczNzM2IDIxMi4yMzkgNy43MjM4MSAyMTEuODMyIDcuNzIzODFIMjA3LjMyNlYyNC45NjE4WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNNzQuNDMwNyA3LjA3ODEyVjI2LjIyOTVIODcuNjMwM1YyMy4zMzc4SDc3LjQyNzVWNy4wNzgxMkg3NC40MzA3WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTQxLjQ4NCA3LjA3ODEyQzEzOC44ODkgNy4wNzgxMiAxMzYuNjg3IDguMDEyOTUgMTM1LjExNiA5Ljc4MjgxQzEzMy41NTkgMTEuNTM2MiAxMzIuNzM3IDEzLjk5NzEgMTMyLjczNyAxNi44OTg5QzEzMi43MzcgMjIuODY1MyAxMzYuMTgyIDI2LjcyMDkgMTQxLjUxMSAyNi43MjA5QzE0NS4yNjYgMjYuNzIwOSAxNDguMTczIDI0Ljc1NzcgMTQ5LjI4OSAyMS40NzA3TDE0OS41NTkgMjAuNjczNUwxNDYuNTg1IDE5LjU0NDJMMTQ2LjMxMSAyMC40MzIzQzE0NS42NDYgMjIuNTgxMSAxNDMuOTQxIDIzLjc2NDggMTQxLjUwOSAyMy43NjQ4QzEzOC4wMzYgMjMuNzY0OCAxMzUuODc4IDIxLjEzNDYgMTM1Ljg3OCAxNi45MDAxQzEzNS44NzggMTIuNjY1NiAxMzguMDU2IDEwLjAzNTUgMTQxLjU2MiAxMC4wMzU1QzE0My45OTMgMTAuMDM1NSAxNDUuMzkzIDEwLjk4OCAxNDYuMTA2IDEzLjEyMjlMMTQ2LjQxNyAxNC4wNTRMMTQ5LjMxMyAxMi42OTU5TDE0OS4wNDggMTEuOTUwNkMxNDcuOTE1IDguNzY0NiAxNDUuMyA3LjA3OTM5IDE0MS40ODMgNy4wNzkzOUwxNDEuNDg0IDcuMDc4MTJaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik05NC42NjU1IDExLjYyMzVDOTEuNzg4NyAxMS42MjM1IDg5LjYzNzQgMTIuOTcxNSA4OC43NjQgMTUuMzIxMkM4OC43MDg0IDE1LjQ3MTUgODguNTQwMyAxNS45MjUgODguNTQwMyAxNS45MjVMOTEuMDA2MyAxNy41MTkzTDkxLjM0MTMgMTYuNjQ2M0M5MS45MTI2IDE1LjE1ODIgOTIuOTY5MyAxNC40NjQ3IDk0LjY2NTUgMTQuNDY0N0M5Ni4zNjE4IDE0LjQ2NDcgOTcuMzMyNSAxNS4yODcgOTcuMzE0OCAxNi45MDY2Qzk3LjMxNDggMTYuOTcyMyA5Ny4zMDk3IDE3LjE3MDYgOTcuMzA5NyAxNy4xNzA2Qzk3LjMwOTcgMTcuMTcwNiA5NS4wNjQ5IDE3LjUzNDQgOTQuMTM5NyAxNy43MzAyQzkwLjE5MjMgMTguNTY0IDg4LjUzOTEgMjAuMDY5OCA4OC41MzkxIDIyLjUzMzJDODguNTM5MSAyMy44NDU4IDg5LjI2ODQgMjUuMjY3IDkwLjU5OTMgMjYuMDY0MUM5MS4zOTgyIDI2LjU0MTYgOTIuNDQwOSAyNi43MjIzIDkzLjU5MjQgMjYuNzIyM0M5NC4zNDk1IDI2LjcyMjMgOTUuMDg1MiAyNi42MDk4IDk1Ljc2NjQgMjYuNDAyNkM5Ny4zMTQ4IDI1Ljg4ODUgOTcuNzQ3MSAyNC44Nzc5IDk3Ljc0NzEgMjQuODc3OVYyNi4xOTkzSDEwMC4zMTJWMTYuNzUyNUMxMDAuMzEyIDEzLjU0MTIgOTguMjAwOCAxMS42MjM1IDk0LjY2NTUgMTEuNjIzNVpNOTcuMzIzNyAyMS43MDQ1Qzk3LjMyMzcgMjIuNjk3NCA5Ni4yNDE3IDI0LjA5NTkgOTMuNzIxMyAyNC4wOTU5QzkzLjAwOTcgMjQuMDk1OSA5Mi41MDU0IDIzLjkwNzcgOTIuMTY5MiAyMy42MjcyQzkxLjcxOTIgMjMuMjUyIDkxLjU3MTMgMjIuNzEyNiA5MS42MzMzIDIyLjIzNjRDOTEuNjU5OCAyMi4wMjkyIDkxLjc4NDkgMjEuNTgzMiA5Mi4yNDg4IDIxLjE5NjdDOTIuNzIyOCAyMC44MDEzIDkzLjU2MDggMjAuNTE4MyA5NC44NTUxIDIwLjIzNjZDOTUuOTE5NCAyMC4wMDU0IDk3LjMyNDkgMTkuNzUwMiA5Ny4zMjQ5IDE5Ljc1MDJWMjEuNzA1OEw5Ny4zMjM3IDIxLjcwNDVaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0xMDkuNzkzIDExLjYyMjFDMTA5LjQzNyAxMS42MjIxIDEwOS4wODkgMTEuNjQ3MyAxMDguNzUyIDExLjY5NDFDMTA2LjQ1NSAxMi4wMzkgMTA1Ljc4MyAxMy4yMDUgMTA1Ljc4MyAxMy4yMDVMMTA1Ljc4NSAxMi4wMjg4SDEwMi45MTFWMjYuMjAxNkgxMDUuOTA4VjE4LjM0NjVDMTA1LjkwOCAxNS42NzcyIDEwNy44NTYgMTQuNDYxOSAxMDkuNjY2IDE0LjQ2MTlDMTExLjYyMiAxNC40NjE5IDExMi41NzMgMTUuNTEzIDExMi41NzMgMTcuNjc3VjI2LjIwMTZIMTE1LjU3VjE3LjI2NTFDMTE1LjU3IDEzLjc4MzUgMTEzLjM1NyAxMS42MjIxIDEwOS43OTUgMTEuNjIyMUgxMDkuNzkzWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTkzLjU5NiAxMS42MjIxQzE5My4yNCAxMS42MjIxIDE5Mi44OTIgMTEuNjQ3MyAxOTIuNTU1IDExLjY5NDFDMTkwLjI1OCAxMi4wMzkgMTg5LjU4NiAxMy4yMDUgMTg5LjU4NiAxMy4yMDVWMTIuMDI3NkgxODYuNzE0VjI2LjIwMTZIMTg5LjcxMVYxOC4zNDY1QzE4OS43MTEgMTUuNjc3MiAxOTEuNjU5IDE0LjQ2MTkgMTkzLjQ2OSAxNC40NjE5QzE5NS40MjUgMTQuNDYxOSAxOTYuMzc2IDE1LjUxMyAxOTYuMzc2IDE3LjY3N1YyNi4yMDE2SDE5OS4zNzNWMTcuMjY1MUMxOTkuMzczIDEzLjc4MzUgMTk3LjE1OSAxMS42MjIxIDE5My41OTcgMTEuNjIyMUgxOTMuNTk2WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTI4LjA3NiAxMi4wMjg4VjEzLjQ4NzlDMTI4LjA3NiAxMy40ODc5IDEyNy4zNDIgMTEuNjIyMSAxMjQuMDAxIDExLjYyMjFDMTE5Ljg1IDExLjYyMjEgMTE3LjI3MSAxNC40ODQ3IDExNy4yNzEgMTkuMDk0NEMxMTcuMjcxIDIxLjY5NTUgMTE4LjEwMyAyMy43NDMyIDExOS41NzEgMjUuMDM2OEMxMjAuNzEyIDI2LjA0MjQgMTIyLjIzNiAyNi41NTc4IDEyNC4wNTEgMjYuNTkzMkMxMjUuMzE0IDI2LjYxNzIgMTI2LjEzMiAyNi4yNzM2IDEyNi42NDMgMjUuOTQ4OUMxMjcuNjIzIDI1LjMyNDkgMTI3Ljk4NyAyNC43MzI0IDEyNy45ODcgMjQuNzMyNEMxMjcuOTg3IDI0LjczMjQgMTI3Ljk0NiAyNS4xOTYgMTI3Ljg3IDI1LjgyMzlDMTI3LjgxNiAyNi4yNzg2IDEyNy43MTMgMjYuNTk4MyAxMjcuNzEzIDI2LjU5ODNDMTI3LjI1NyAyOC4yMjE2IDEyNS45MjIgMjkuMTYwMiAxMjMuOTc2IDI5LjE2MDJDMTIyLjAyOSAyOS4xNjAyIDEyMC44NSAyOC41MTk3IDEyMC42MTYgMjcuMjU3N0wxMTcuNzAyIDI4LjEyNjhDMTE4LjIwNiAzMC41NTIzIDEyMC40ODMgMzIgMTIzLjc5NSAzMkMxMjYuMDQ2IDMyIDEyNy44MSAzMS4zODg2IDEyOS4wNCAzMC4xODA5QzEzMC4yOCAyOC45NjMxIDEzMC45MSAyNy4yMDg0IDEzMC45MSAyNC45NjQ4VjEyLjAyNzZIMTI4LjA3NlYxMi4wMjg4Wk0xMjcuODg2IDE5LjIyMzJDMTI3Ljg4NiAyMi4wNTggMTI2LjUwMSAyMy43NTA4IDEyNC4xOCAyMy43NTA4QzEyMS42OTQgMjMuNzUwOCAxMjAuMjY4IDIyLjA1MyAxMjAuMjY4IDE5LjA5NDRDMTIwLjI2OCAxNi4xMzU4IDEyMS42OTQgMTQuNDYzMiAxMjQuMTggMTQuNDYzMkMxMjYuNDQ1IDE0LjQ2MzIgMTI3Ljg2NSAxNi4xNDg0IDEyNy44ODYgMTguODYxOVYxOS4yMjMyWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTU4LjE5MiAxMS42MjIxQzE1Ny44NjMgMTEuNjIyMSAxNTcuNTQzIDExLjY0MzYgMTU3LjIzMyAxMS42ODRDMTU0Ljk3MyAxMi4wMzY1IDE1NC4zMDggMTMuMTg3MyAxNTQuMzA4IDEzLjE4NzNWMTIuODUwMUgxNTQuMzA2VjcuMDc4MTJIMTUxLjMxVjI2LjIwMjlIMTU0LjMwNlYxOC4zNDc4QzE1NC4zMDYgMTUuNjYwOSAxNTYuMjU0IDE0LjQzOCAxNTguMDY0IDE0LjQzOEMxNjAuMDIxIDE0LjQzOCAxNjAuOTcxIDE1LjQ4OSAxNjAuOTcxIDE3LjY1M1YyNi4yMDI5SDE2My45NjhWMTcuMjQxMkMxNjMuOTY4IDEzLjgyOTEgMTYxLjcwMSAxMS42MjM0IDE1OC4xOTMgMTEuNjIzNEwxNTguMTkyIDExLjYyMjFaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0xODIuNDQ4IDEwLjk2NTRDMTgzLjUyMSAxMC45NjU0IDE4NC4zOSAxMC4wOTYgMTg0LjM5IDkuMDIzNjlDMTg0LjM5IDcuOTUxMzQgMTgzLjUyMSA3LjA4MjAzIDE4Mi40NDggNy4wODIwM0MxODEuMzc1IDcuMDgyMDMgMTgwLjUwNSA3Ljk1MTM0IDE4MC41MDUgOS4wMjM2OUMxODAuNTA1IDEwLjA5NiAxODEuMzc1IDEwLjk2NTQgMTgyLjQ0OCAxMC45NjU0WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTgwLjk1OCAxMi4wMjE1VjE5LjIxNDZDMTgwLjEwNSAxOC41MTIyIDE3OS4xMTIgMTcuOTgyOSAxNzcuOTg3IDE3LjY2NThWMTYuNzUyNUMxNzcuOTg3IDEzLjU0MTIgMTc1Ljg3NyAxMS42MjM1IDE3Mi4zNDEgMTEuNjIzNUMxNjkuNDY1IDExLjYyMzUgMTY3LjMxMyAxMi45NzE1IDE2Ni40NCAxNS4zMjEyQzE2Ni4zODQgMTUuNDcxNSAxNjYuMjE2IDE1LjkyNSAxNjYuMjE2IDE1LjkyNUwxNjguNjgyIDE3LjUxOTNMMTY5LjAxNyAxNi42NDYzQzE2OS41ODggMTUuMTU4MiAxNzAuNjQ1IDE0LjQ2NDcgMTcyLjM0MSAxNC40NjQ3QzE3NC4wMzggMTQuNDY0NyAxNzUuMDA4IDE1LjI4NyAxNzQuOTkxIDE2LjkwNjZDMTc0Ljk5MSAxNi45MTY3IDE3NC45OTEgMTcuMDUxOCAxNzQuOTkxIDE3LjI2NzlDMTczLjcyMiAxNy4yMzI1IDE3Mi41NDEgMTcuMzU1IDE3MS40ODEgMTcuNjAzOUMxNzAuMDgzIDE3LjkxOTcgMTY3LjQ4NiAxOC43MjE5IDE2Ni41NTkgMjAuODA3NkMxNjYuNTUyIDIwLjgyMTUgMTY2LjQxNiAyMS4xODE1IDE2Ni40MTYgMjEuMTgxNUMxNjYuMjgyIDIxLjU5NTkgMTY2LjIxNSAyMi4wNDU2IDE2Ni4yMTUgMjIuNTMzMkMxNjYuMjE1IDIzLjg0NTggMTY2Ljk0NCAyNS4yNjcgMTY4LjI3NSAyNi4wNjQxQzE2OS4wNzQgMjYuNTQxNiAxNzAuMTE3IDI2LjcyMjMgMTcxLjI2OCAyNi43MjIzQzE3Mi4wMTEgMjYuNzIyMyAxNzIuNzM0IDI2LjYxMzYgMTczLjQwNiAyNi40MTRDMTc0Ljk4NCAyNS45MDM3IDE3NS40MjMgMjQuODc3OSAxNzUuNDIzIDI0Ljg3NzlWMjYuMjAwNUgxNzcuOTg3VjIxLjg3MTNDMTc3LjI2NyAyMS40MjE1IDE3Ni4xODUgMjEuMTU2MiAxNzQuOTk4IDIxLjE1ODhDMTc0Ljk5OCAyMS40OTM1IDE3NC45OTggMjEuNzA1OCAxNzQuOTk4IDIxLjcwNThDMTc0Ljk5OCAyMi42OTg3IDE3My45MTYgMjQuMDk3MiAxNzEuMzk2IDI0LjA5NzJDMTcwLjY4NCAyNC4wOTcyIDE3MC4xOCAyMy45MDg5IDE2OS44NDQgMjMuNjI4NUMxNjkuMzk0IDIzLjI1MzMgMTY5LjI0NiAyMi43MTM5IDE2OS4zMDggMjIuMjM3NkMxNjkuMzM0IDIyLjAzMDQgMTY5LjQ1OSAyMS41ODQ1IDE2OS45MjMgMjEuMTk3OUwxNjkuOTE4IDIxLjE4NEMxNzAuOTgzIDIwLjMxMzYgMTczLjA3NCAxOS45NjYyIDE3NC45OTYgMjAuMDQyVjIwLjA0NThDMTc2LjYzMSAyMC4xMDUyIDE3Ny44NTUgMjAuNDI2MSAxNzguNzI4IDIxLjAyNzRDMTc4Ljk2NiAyMS4xNzc3IDE3OS4xODkgMjEuMzQ1NyAxNzkuMzk2IDIxLjUzMDJDMTgwLjI3MyAyMi4zMTcyIDE4MC42MjUgMjMuMjg2MSAxODAuNzc3IDIzLjg1MjFDMTgxLjAyNCAyNC43NzU1IDE4MC45NTggMjYuMTk4IDE4MC45NTggMjYuMTk4SDE4My45MzlWMTIuMDI0SDE4MC45NThWMTIuMDIxNVoiIGZpbGw9IiMxQzNDM0MiLz4KPC9zdmc+){.nav-logo .w-auto .relative .object-contain .block .dark:hidden .h-6}![dark logo](data:,){.nav-logo .w-auto .relative .object-contain .hidden .dark:block .h-6 .sf-hidden}](https://docs.langchain.com/)

::: {.hidden .lg:flex .items-center .gap-x-2}
:::

[LangChain + LangGraph]{.truncate .max-w-[12.5rem] title="LangChain + LangGraph"}
:::

::: {.relative .hidden .lg:flex .items-center .flex-1 .z-20 .justify-center}
::: {.flex .items-center .gap-2 .min-w-[42px]}
::: {.truncate .min-w-0}
Search\...
:::
:::

[Ctrl K]{.flex-none .text-xs .font-semibold}
:::

::: {.topbar-right-container .hidden .lg:flex .flex-1 .items-center .gap-2 .ml-auto .justify-end}
::: {.flex .relative .items-center .justify-end .space-x-4}
-   Ask AI
-   GitHub
-   -   [[[]{.absolute .inset-0 .bg-primary-dark .rounded-xl .group-hover:opacity-[0.9]}](https://smith.langchain.com/){.group .px-4 .py-1.5 .relative .inline-flex .items-center .text-sm .font-medium}]{#topbar-cta-button}
    ::: {.mr-0.5 .space-x-2.5 .flex .items-center}
    [Try LangSmith]{.z-10 .text-white}
    :::
:::
:::

::: {.flex .lg:hidden .items-center .gap-3 .sf-hidden}
:::
:::
:::
:::

::: {.hidden .lg:flex .px-4 .h-10}
::: {.nav-tabs .h-full .flex .text-sm .gap-x-6}
[LangChain](https://docs.langchain.com/oss/python/langchain/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::

[LangGraph](https://docs.langchain.com/oss/python/langgraph/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::

[Deep Agents](https://docs.langchain.com/oss/python/deepagents/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .[text-shadow:-0.2px_0_0_currentColor,0.2px_0_0_currentColor] .text-primary .dark:text-primary-light .hover:text-primary .dark:hover:text-primary-light}

::: {.absolute .bottom-0 .w-full .left-0 .bg-primary .dark:bg-primary-light .h-px}
:::

[Integrations](https://docs.langchain.com/oss/python/integrations/providers/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::

[Learn](https://docs.langchain.com/oss/python/learn){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::

[Reference](https://docs.langchain.com/oss/python/reference/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::

[Contribute](https://docs.langchain.com/oss/python/contributing/overview){.link .nav-tabs-item .group .relative .h-full .gap-2 .flex .items-center .font-medium .hover:text-gray-800 .dark:hover:text-gray-300 .text-gray-800 .dark:text-gray-200}

::: {.absolute .bottom-0 .w-full .left-0 .group-hover:bg-gray-200 .dark:group-hover:bg-gray-700 .h-px}
:::
:::
:::
:::
:::

::: {.peer-[.is-custom]:max-w-none .peer-[.is-not-custom]:max-w-8xl .peer-[.is-not-custom]:lg:flex .peer-[.is-not-custom]:mx-auto .peer-[.is-not-custom]:px-0 .peer-[.is-not-custom]:lg:px-5 .peer-[.is-custom]:[&>div:first-child]:!hidden .peer-[.is-custom]:[&>div:first-child]:sm:!hidden .peer-[.is-custom]:[&>div:first-child]:md:!hidden .peer-[.is-custom]:[&>div:first-child]:lg:!hidden .peer-[.is-custom]:[&>div:first-child]:xl:!hidden}
::: {#sidebar-content .hidden .sticky .shrink-0 .w-[18rem] .lg:flex .flex-col .left-0 .top-[7rem] .bottom-0 .right-auto .border-r .border-gray-100 .dark:border-white/10 .transition-transform .duration-100 style="top:8.5rem;height:calc(100vh - 8.5rem)"}
::: {#navigation-items .flex-1 .pr-5 .pt-5 .pb-4 .overflow-y-auto .stable-scrollbar-gutter}
::: {.sticky .-top-[24px] .h-8 .-mt-8 .left-0 .right-0 .pointer-events-none .transition-opacity .duration-50 .z-10 .bg-gradient-to-b .from-background-light .dark:from-background-dark .opacity-0 aria-hidden="true"}
:::

::: {.text-sm .relative}
::: {.pl-2}
::: {.nav-dropdown-item-icon .h-8 .w-8 .flex .items-center .justify-center .rounded-lg .flex-shrink-0 .border .border-gray-200/70 .dark:border-white/[0.07]}
:::

::: {.nav-dropdown-item-text-container .flex-1 .px-1 .flex .flex-col .grow .text-left}
Python
:::
:::

<!-- -->

-   [[](https://docs.langchain.com/oss/python/deepagents/overview){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .bg-primary/10 .text-primary .[text-shadow:-0.2px_0_0_currentColor,0.2px_0_0_currentColor] .dark:text-primary-light .dark:bg-primary-light/10}]{#/oss/python/deepagents/overview}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Overview

    </div>
    :::

::: {.px-1 .py-3}
::: {.sidebar-nav-group-divider .h-px .w-full .bg-gray-100 .dark:bg-white/10}
:::
:::

::: {.my-2}
::: {.sidebar-group-header .flex .items-center .gap-2.5 .pl-4 .mb-3.5 .lg:mb-2.5 .font-semibold .text-gray-700 .dark:text-gray-300 .text-xs}
##### Get started {#sidebar-title}
:::

-   [[](https://docs.langchain.com/oss/python/deepagents/quickstart){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/quickstart}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Quickstart

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/customization){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/customization}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Customization

    </div>
    :::
:::

::: {.px-1 .py-3}
::: {.sidebar-nav-group-divider .h-px .w-full .bg-gray-100 .dark:bg-white/10}
:::
:::

::: {.my-2}
::: {.sidebar-group-header .flex .items-center .gap-2.5 .pl-4 .mb-3.5 .lg:mb-2.5 .font-semibold .text-gray-700 .dark:text-gray-300 .text-xs}
##### Core capabilities {#sidebar-title}
:::

-   [[](https://docs.langchain.com/oss/python/deepagents/harness){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/harness}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Agent harness

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/backends){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/backends}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Backends

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/subagents){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/subagents}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Subagents

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/human-in-the-loop){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/human-in-the-loop}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Human-in-the-loop

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/long-term-memory){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/long-term-memory}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Long-term memory

    </div>
    :::

-   [[](https://docs.langchain.com/oss/python/deepagents/middleware){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/middleware}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Middleware

    </div>
    :::
:::

::: {.px-1 .py-3}
::: {.sidebar-nav-group-divider .h-px .w-full .bg-gray-100 .dark:bg-white/10}
:::
:::

::: {.my-2}
::: {.sidebar-group-header .flex .items-center .gap-2.5 .pl-4 .mb-3.5 .lg:mb-2.5 .font-semibold .text-gray-700 .dark:text-gray-300 .text-xs}
##### Command line interface {#sidebar-title}
:::

-   [[](https://docs.langchain.com/oss/python/deepagents/cli){.group .flex .items-center .pr-3 .py-1.5 .cursor-pointer .gap-x-3 .text-left .rounded-xl .w-full .outline-offset-[-1px] .hover:bg-gray-600/5 .dark:hover:bg-gray-200/5 .text-gray-700 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}]{#/oss/python/deepagents/cli}
    ::: {.flex-1 .flex .items-center .space-x-2.5}
    <div>

    Use the CLI

    </div>
    :::
:::
:::
:::
:::

[]{.fixed .inset-0 .bg-background-light .dark:bg-background-dark .-z-10 .pointer-events-none}

::: {.w-full}
::: {#content-container .px-5 .lg:pr-10 .lg:pl-[5.5rem] .lg:pt-10 .mx-auto .max-w-6xl .flex .flex-row-reverse .gap-x-12 .w-full .pt-[200px]}
::: {#content-side-layout .hidden .xl:flex .self-start .sticky .xl:flex-col .max-w-[28rem] .h-[calc(100vh-15rem)] .top-[calc(12rem-var(--sidenav-move-up,0px))]}
::: {#table-of-contents-layout .z-10 .hidden .xl:flex .pl-10 .box-border .w-[19rem] .max-h-full}
::: {#table-of-contents .text-gray-600 .text-sm .leading-6 .w-[16.5rem] .overflow-y-auto .space-y-2 .pb-4 .-mt-10 .pt-10}
On this page

-   [When to use deep agents](#when-to-use-deep-agents){.py-1 .block .border-l .pl-4 .font-medium .text-primary .dark:text-primary-light .border-primary .dark:border-primary-light .hover:border-primary .dark:hover:border-primary-light}
-   [Core capabilities](#core-capabilities){.py-1 .block .border-l .pl-4 .border-gray-950/5 .dark:border-white/10 .hover:border-gray-950/20 .dark:hover:border-white/20 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}
-   [Relationship to the LangChain ecosystem](#relationship-to-the-langchain-ecosystem){.py-1 .block .border-l .pl-4 .border-gray-950/5 .dark:border-white/10 .hover:border-gray-950/20 .dark:hover:border-white/20 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}
-   [Get started](#get-started){.py-1 .block .border-l .pl-4 .border-gray-950/5 .dark:border-white/10 .hover:border-gray-950/20 .dark:hover:border-white/20 .hover:text-gray-900 .dark:text-gray-400 .dark:hover:text-gray-300}
:::
:::
:::

::: {#content-area .grow .w-full .mx-auto .xl:w-[calc(100%-28rem)]}
::: {.mt-0.5 .space-y-2.5}
::: {.flex .flex-col .sm:flex-row .items-start .sm:items-center .relative .gap-2}
Deep Agents overview {#page-title .inline-block .text-2xl .sm:text-3xl .font-bold .text-gray-900 .tracking-tight .dark:text-gray-200}
====================

::: {#page-context-menu .items-center .shrink-0 .min-w-[156px] .justify-end .ml-auto .sm:flex .hidden}
::: {.flex .items-center .gap-2 .text-sm .text-center .font-medium}
Copy page
:::
:::
:::
:::

::: {.mt-2 .text-lg .prose .prose-gray .dark:prose-invert .[&>*]:[overflow-wrap:anywhere]}
Build agents that can plan, use subagents, and leverage file systems for complex tasks
:::

::: {#page-context-menu .flex .items-center .shrink-0 .min-w-[156px] .mt-3 .sm:hidden .sf-hidden}
:::

::: {#content .mdx-content .relative .mt-8 .mb-14 .prose .prose-gray .dark:prose-invert data-page-title="Deep Agents overview" data-page-href="/oss/python/deepagents/overview"}
[[`deepagents`](https://pypi.org/project/deepagents/){.link} is a standalone library for building agents that can tackle complex, multi-step tasks. Built on LangGraph and inspired by applications like Claude Code, Deep Research, and Manus, deep agents come with planning capabilities, file systems for context management, and the ability to spawn subagents.]{data-as="p"}

 {#when-to-use-deep-agents .flex .whitespace-pre-wrap .group .font-semibold}

::: {.absolute tabindex="-1"}
[​](#when-to-use-deep-agents){.-ml-10 .flex .items-center .opacity-0 .border-0 .group-hover:opacity-100 .focus:opacity-100 .focus:outline-0 .group/link}

::: {.w-6 .h-6 .rounded-md .flex .items-center .justify-center .shadow-sm .text-gray-400 .dark:text-white/50 .dark:bg-background-dark .dark:brightness-[1.35] .dark:ring-1 .dark:hover:brightness-150 .bg-white .ring-1 .ring-gray-400/30 .dark:ring-gray-700/25 .hover:ring-gray-400/60 .dark:hover:ring-white/20 .group-focus/link:border-2 .group-focus/link:border-primary .dark:group-focus/link:border-primary-light}
:::
:::

[When to use deep agents]{.cursor-pointer}

[Use deep agents when you need agents that can:]{data-as="p"}

-   **Handle complex, multi-step tasks** that require planning and decomposition
-   **Manage large amounts of context** through file system tools
-   **Delegate work** to specialized subagents for context isolation
-   **Persist memory** across conversations and threads

[For simpler use cases, consider using LangChain's [`create_agent`](https://docs.langchain.com/oss/python/langchain/agents){.link} or building a custom [LangGraph](https://docs.langchain.com/oss/python/langgraph/overview){.link} workflow.]{data-as="p"}

 {#core-capabilities .flex .whitespace-pre-wrap .group .font-semibold}

::: {.absolute tabindex="-1"}
[​](#core-capabilities){.-ml-10 .flex .items-center .opacity-0 .border-0 .group-hover:opacity-100 .focus:opacity-100 .focus:outline-0 .group/link}

::: {.w-6 .h-6 .rounded-md .flex .items-center .justify-center .shadow-sm .text-gray-400 .dark:text-white/50 .dark:bg-background-dark .dark:brightness-[1.35] .dark:ring-1 .dark:hover:brightness-150 .bg-white .ring-1 .ring-gray-400/30 .dark:ring-gray-700/25 .hover:ring-gray-400/60 .dark:hover:ring-white/20 .group-focus/link:border-2 .group-focus/link:border-primary .dark:group-focus/link:border-primary-light}
:::
:::

[Core capabilities]{.cursor-pointer}

::: {.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full}
::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Planning and task decomposition {#planning-and-task-decomposition .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
-------------------------------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[Deep agents include a built-in `write_todos` tool that enables agents to break down complex tasks into discrete steps, track progress, and adapt plans as new information emerges.]{data-as="p"}
:::

</div>
:::
:::

::: {.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full}
::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Context management {#context-management .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
------------------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[File system tools (`ls`, `read_file`, `write_file`, `edit_file`) allow agents to offload large context to memory, preventing context window overflow and enabling work with variable-length tool results.]{data-as="p"}
:::

</div>
:::
:::

::: {.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full}
::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Subagent spawning {#subagent-spawning .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
-----------------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[A built-in `task` tool enables agents to spawn specialized subagents for context isolation. This keeps the main agent's context clean while still going deep on specific subtasks.]{data-as="p"}
:::

</div>
:::
:::

::: {.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full}
::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Long-term memory {#long-term-memory .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
----------------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[Extend agents with persistent memory across threads using LangGraph's Store. Agents can save and retrieve information from previous conversations.]{data-as="p"}
:::

</div>
:::
:::

 {#relationship-to-the-langchain-ecosystem .flex .whitespace-pre-wrap .group .font-semibold}

::: {.absolute tabindex="-1"}
[​](#relationship-to-the-langchain-ecosystem){.-ml-10 .flex .items-center .opacity-0 .border-0 .group-hover:opacity-100 .focus:opacity-100 .focus:outline-0 .group/link}

::: {.w-6 .h-6 .rounded-md .flex .items-center .justify-center .shadow-sm .text-gray-400 .dark:text-white/50 .dark:bg-background-dark .dark:brightness-[1.35] .dark:ring-1 .dark:hover:brightness-150 .bg-white .ring-1 .ring-gray-400/30 .dark:ring-gray-700/25 .hover:ring-gray-400/60 .dark:hover:ring-white/20 .group-focus/link:border-2 .group-focus/link:border-primary .dark:group-focus/link:border-primary-light}
:::
:::

[Relationship to the LangChain ecosystem]{.cursor-pointer}

[Deep agents is built on top of:]{data-as="p"}

-   [LangGraph](https://docs.langchain.com/oss/python/langgraph/overview){.link} - Provides the underlying graph execution and state management
-   [LangChain](https://docs.langchain.com/oss/python/langchain/overview){.link} - Tools and model integrations work seamlessly with deep agents
-   [LangSmith](https://docs.langchain.com/langsmith/home){.link} - Observability, evaluation, and deployment

[Deep agents applications can be deployed via [LangSmith Deployment](https://docs.langchain.com/langsmith/deployments){.link} and monitored with [LangSmith Observability](https://docs.langchain.com/langsmith/observability){.link}.]{data-as="p"}

 {#get-started .flex .whitespace-pre-wrap .group .font-semibold}

::: {.absolute tabindex="-1"}
[​](#get-started){.-ml-10 .flex .items-center .opacity-0 .border-0 .group-hover:opacity-100 .focus:opacity-100 .focus:outline-0 .group/link}

::: {.w-6 .h-6 .rounded-md .flex .items-center .justify-center .shadow-sm .text-gray-400 .dark:text-white/50 .dark:bg-background-dark .dark:brightness-[1.35] .dark:ring-1 .dark:hover:brightness-150 .bg-white .ring-1 .ring-gray-400/30 .dark:ring-gray-700/25 .hover:ring-gray-400/60 .dark:hover:ring-white/20 .group-focus/link:border-2 .group-focus/link:border-primary .dark:group-focus/link:border-primary-light}
:::
:::

[Get started]{.cursor-pointer}

::: {.card-group .prose .dark:prose-dark .grid .gap-x-4 .sm:grid-cols-2}
[](https://docs.langchain.com/oss/python/deepagents/quickstart){.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full .cursor-pointer .hover:!border-primary .dark:hover:!border-primary-light}

::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {#card-link-arrow-icon .absolute .text-gray-400 .dark:text-gray-500 .group-hover:text-primary .dark:group-hover:text-primary-light .top-5 .right-5 .hidden .sf-hidden}
:::

::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Quickstart {#quickstart .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
----------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[Build your first deep agent]{data-as="p"}
:::

</div>
:::

[](https://docs.langchain.com/oss/python/deepagents/customization){.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full .cursor-pointer .hover:!border-primary .dark:hover:!border-primary-light}

::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {#card-link-arrow-icon .absolute .text-gray-400 .dark:text-gray-500 .group-hover:text-primary .dark:group-hover:text-primary-light .top-5 .right-5 .hidden .sf-hidden}
:::

::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Customization {#customization .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
-------------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[Learn about customization options]{data-as="p"}
:::

</div>
:::

[](https://docs.langchain.com/oss/python/deepagents/middleware){.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full .cursor-pointer .hover:!border-primary .dark:hover:!border-primary-light}

::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {#card-link-arrow-icon .absolute .text-gray-400 .dark:text-gray-500 .group-hover:text-primary .dark:group-hover:text-primary-light .top-5 .right-5 .hidden .sf-hidden}
:::

::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Middleware {#middleware .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
----------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[Understand the middleware architecture]{data-as="p"}
:::

</div>
:::

[](https://reference.langchain.com/python/deepagents/){.card .block .font-normal .group .relative .my-2 .ring-2 .ring-transparent .rounded-2xl .bg-white .dark:bg-background-dark .border .border-gray-950/10 .dark:border-white/10 .overflow-hidden .w-full .cursor-pointer .hover:!border-primary .dark:hover:!border-primary-light}

::: {.px-6 .py-5 .relative data-component-part="card-content-container"}
::: {#card-link-arrow-icon .absolute .text-gray-400 .dark:text-gray-500 .group-hover:text-primary .dark:group-hover:text-primary-light .top-5 .right-5}
:::

::: {.h-6 .w-6 .fill-gray-800 .dark:fill-gray-100 .text-gray-800 .dark:text-gray-100 data-component-part="card-icon"}
:::

<div>

Reference {#reference .not-prose .font-semibold .text-base .text-gray-800 .dark:text-white .mt-4 contenteditable="false" data-component-part="card-title"}
---------

::: {.prose .mt-1 .font-normal .text-base .leading-6 .text-gray-600 .dark:text-gray-400 data-component-part="card-content"}
[See the `deepagents` API reference]{data-as="p"}
:::

</div>
:::
:::

------------------------------------------------------------------------

::: {.callout .my-4 .px-5 .py-4 .overflow-hidden .rounded-2xl .flex .gap-3 .border .border-zinc-500/20 .bg-zinc-50/50 .dark:border-zinc-500/30 .dark:bg-zinc-500/10 data-callout-type="callout"}
::: {.mt-0.5 .w-4 data-component-part="callout-icon"}
:::

::: {.text-sm .prose .dark:prose-invert .min-w-0 .w-full .[&_kbd]:bg-background-light .dark:[&_kbd]:bg-background-dark .[&_code]:!text-current .[&_kbd]:!text-current .[&_a]:!text-current .[&_a]:border-current .text-zinc-900 .dark:text-zinc-200 data-component-part="callout-content"}
[[Edit the source of this page on GitHub.](https://github.com/langchain-ai/docs/edit/main/src/oss/deepagents/overview.mdx){.link}]{data-as="p"}
:::
:::

::: {.callout .my-4 .px-5 .py-4 .overflow-hidden .rounded-2xl .flex .gap-3 .border .border-emerald-500/20 .bg-emerald-50/50 .dark:border-emerald-500/30 .dark:bg-emerald-500/10 .[&_[data-component-part='callout-icon']]:mt-px data-callout-type="tip"}
::: {.mt-0.5 .w-4 data-component-part="callout-icon"}
:::

::: {.text-sm .prose .dark:prose-invert .min-w-0 .w-full .[&_kbd]:bg-background-light .dark:[&_kbd]:bg-background-dark .[&_code]:!text-current .[&_kbd]:!text-current .[&_a]:!text-current .[&_a]:border-current .text-emerald-900 .dark:text-emerald-200 data-component-part="callout-content"}
[[Connect these docs programmatically](https://docs.langchain.com/use-these-docs){.link} to Claude, VSCode, and more via MCP for real-time answers.]{data-as="p"}
:::
:::
:::

::: {.feedback-toolbar .pb-16 .w-full .flex .flex-col .gap-y-8}
::: {.flex .flex-col .gap-4 .xl:flex-col .xl:gap-6 .min-[1400px]:flex-row .min-[1400px]:items-center .md:flex-row .md:justify-end}
::: {.w-full .flex .flex-col .gap-y-6}
::: {.flex .flex-row .gap-5 .items-center .grow .justify-between .md:justify-start .xl:justify-between .min-[1400px]:justify-start}
Was this page helpful?

::: {.flex .flex-row .gap-3 .items-center}
Yes

No
:::
:::
:::

::: {.flex .flex-row .gap-3 .justify-end}
:::
:::
:::

::: {#pagination .grid .lg:grid-cols-2 .gap-4 .sf-hidden}
:::

::: {.left-0 .right-0 .sticky .sm:px-4 .pb-4 .sm:pb-6 .bottom-0 .pt-1 .flex .flex-col .items-center .w-full .overflow-hidden .z-20}
::: {.chat-assistant-floating-input .z-10 .w-full .sm:w-80 .focus-within:w-full .sm:focus-within:w-[26rem] .hover:scale-100 .sm:hover:scale-105 .focus-within:hover:scale-100 .[transition:width_400ms,left_200ms,transform_500ms,opacity_200ms]}
::: {.transition-all .duration-300 .translate-y-[100px] .opacity-0}
::: {.pl-5 .pr-3 .border .border-gray-950/20 .dark:border-white/20 .rounded-2xl .bg-background-light/90 .dark:bg-background-dark/90 .backdrop-blur-xl .shadow-2xl .shadow-gray-900/5 .flex .items-center .justify-between .focus-within:border-primary .dark:focus-within:border-primary-light .transition-colors .duration-400}
[Ctrl+I]{.text-xs .font-semibold .select-none .pointer-events-none .hidden .lg:inline .ml-2 .mr-1}
:::
:::
:::
:::
:::
:::

::: {.flex .w-full .flex-col .gap-12 .justify-between .px-8 .py-16 .md:py-20 .lg:py-28 .max-w-[984px] .z-0}
::: {.flex .flex-col .md:flex-row .gap-8 .justify-between .min-h-[76px]}
::: {.flex .md:flex-col .justify-between .items-center .md:items-start .min-w-16 .md:min-w-20 .lg:min-w-48 .md:gap-y-24}
[[Docs by LangChain home page]{.sr-only}![light logo](data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNjUiIGhlaWdodD0iMzIiIHZpZXdCb3g9IjAgMCAyNjUgMzIiIGZpbGw9Im5vbmUiPgo8cGF0aCBkPSJNNDkuNzM5NyA5LjQ5OTg3QzUwLjk2MDcgMTAuNzIwMiA1MC45NjA3IDEyLjcwNjEgNDkuNzM5NyAxMy45MjY0TDQ3LjAwNDUgMTYuNjE1OUw0Ni45NzY3IDE2LjQ2MThDNDYuNzc3IDE1LjM1NjQgNDYuMjUxMiAxNC4zNTM0IDQ1LjQ1NzQgMTMuNTYwMUM0NC44NTk2IDEyLjk2MzggNDQuMTUzIDEyLjUyMjkgNDMuMzU2NyAxMi4yNUM0Mi44NjI1IDEyLjc0NjUgNDIuNTkwNyAxMy4zOTcxIDQyLjU5MDcgMTQuMDgxOEM0Mi41OTA3IDE0LjIyMDcgNDIuNjAzNCAxNC4zNjQ4IDQyLjYyODcgMTQuNTA4OEM0My4wNjcyIDE0LjY2NjcgNDMuNDU1MyAxNC45MTA1IDQzLjc4MTQgMTUuMjM2NEM0NS4wMDI0IDE2LjQ1NjggNDUuMDAyNCAxOC40NDI2IDQzLjc4MTQgMTkuNjYzTDQxLjQwMDEgMjIuMDQzQzQwLjc4OTYgMjIuNjUzMSAzOS45ODgyIDIyLjk1NzYgMzkuMTg1NiAyMi45NTc2QzM4LjM4MyAyMi45NTc2IDM3LjU4MTYgMjIuNjUzMSAzNi45NzExIDIyLjA0M0MzNS43NTAxIDIwLjgyMjcgMzUuNzUwMSAxOC44MzY4IDM2Ljk3MTEgMTcuNjE2NEwzOS43MDY0IDE0LjkyODJMMzkuNzM0MiAxNS4wODIzQzM5LjkzMjYgMTYuMTg1MSA0MC40NTg0IDE3LjE4ODIgNDEuMjU0NyAxNy45ODI4QzQxLjg1MzggMTguNTgxNiA0Mi41MTc0IDE4Ljk3OTUgNDMuMzEyNSAxOS4yNTExTDQzLjQ1OTEgMTkuMTA0NkM0My45MDQgMTguNjU5OSA0NC4xNDc5IDE4LjA2ODcgNDQuMTQ3OSAxNy40MzgzQzQ0LjE0NzkgMTcuMjk4MSA0NC4xMzUzIDE3LjE1NzkgNDQuMTExMyAxNy4wMjAyQzQzLjY1MjUgMTYuODY4NiA0My4yNzQ1IDE2LjY1MjYgNDIuOTMwNyAxNi4zMDlDNDIuNDM1MyAxNS44MTM3IDQyLjEyNjkgMTUuMTgwOCA0Mi4wNDA5IDE0LjQ3OTdDNDIuMDM0NiAxNC40MjkyIDQyLjAzMDggMTQuMzc5OSA0Mi4wMjU3IDE0LjMyOTRDNDEuOTU3NSAxMy40MTYgNDIuMjg3NCAxMi41MjQyIDQyLjkzMDcgMTEuODgyNEw0NS4zMTIxIDkuNTAyMzlDNDUuOTAyMyA4LjkxMjQ0IDQ2LjY4ODUgOC41ODY1MiA0Ny41MjY1IDguNTg2NTJDNDguMzY0NSA4LjU4NjUyIDQ5LjE1MDcgOC45MTExOCA0OS43NDEgOS41MDIzOUw0OS43Mzk3IDkuNDk5ODdaTTYyLjE3NDcgMTUuNzkxQzYyLjE3NDcgMjQuNDk4OCA1NS4wODYzIDMxLjU4MiA0Ni4zNzUxIDMxLjU4MkgxNS43OTk2QzcuMDg4MzQgMzEuNTgyIDAgMjQuNDk4OCAwIDE1Ljc5MUMwIDcuMDgzMjEgNy4wODgzNCAwIDE1Ljc5OTYgMEg0Ni4zNzUxQzU1LjA4NzYgMCA2Mi4xNzQ3IDcuMDg0NDggNjIuMTc0NyAxNS43OTFaTTMwLjQ0OSAyMy43MTA1QzMwLjY5OCAyMy40MDg2IDI5LjU0NzggMjIuNTU4NCAyOS4zMTI3IDIyLjI0NjRDMjguODM0OSAyMS43Mjg0IDI4LjgzMjQgMjAuOTgzMSAyOC41MTAxIDIwLjM3OEMyNy43MjE0IDE4LjU1MTMgMjYuODE1MSAxNi43Mzg1IDI1LjU0NzQgMTUuMTkyMkMyNC4yMDc2IDEzLjUwMDcgMjIuNTU0MyAxMi4xMDEgMjEuMTAyIDEwLjUxM0MyMC4wMjM4IDkuNDA1MTIgMTkuNzM1NiA3LjgyNzI4IDE4Ljc4MzkgNi42MzYwMUMxNy40NzE5IDQuNjk5NCAxMy4zMjM1IDQuMTcxMzUgMTIuNzE1NSA2LjkwNjM1QzEyLjcxODEgNi45OTIyNiAxMi42OTE1IDcuMDQ2NTggMTIuNjE2OSA3LjEwMDlDMTIuMjgwNyA3LjM0NDcxIDExLjk4MTIgNy42MjM5IDExLjcyOTYgNy45NjExOUMxMS4xMTQxIDguODE3NyAxMS4wMTkzIDEwLjI3MDUgMTEuNzg3OCAxMS4wMzk4QzExLjgxMzEgMTAuNjM0MyAxMS44MjcgMTAuMjUxNSAxMi4xNDggOS45NjA5N0MxMi43NDIxIDEwLjQ3MDEgMTMuNjM5NSAxMC42NTA3IDE0LjMyODQgMTAuMjcwNUMxNS44NTAyIDEyLjQ0MiAxNS40NzEgMTUuNDQ2MSAxNi42NzkzIDE3Ljc4NTdDMTcuMDEzIDE4LjMzOSAxNy4zNDkzIDE4LjkwMzcgMTcuNzc3NyAxOS4zODg4QzE4LjEyNTMgMTkuOTI5NSAxOS4zMjYxIDIwLjU2NzUgMTkuMzk2OSAyMS4wNjc3QzE5LjQwOTUgMjEuOTI2OCAxOS4zMDg0IDIyLjg2NTQgMTkuODcyMSAyMy41ODQyQzIwLjEzNzYgMjQuMTIyMyAxOS40ODU0IDI0LjY2MyAxOC45NTk1IDI0LjU5NjFDMTguMjc3IDI0LjY4OTYgMTcuNDQ0IDI0LjEzNzUgMTYuODQ2MiAyNC40NzczQzE2LjYzNTEgMjQuNzA2IDE2LjIyMTggMjQuNDUzMyAxNi4wMzk4IDI0Ljc3MDRDMTUuOTc2NiAyNC45MzQ2IDE1LjYzNTMgMjUuMTY1OCAxNS44Mzg4IDI1LjMyMzdDMTYuMDY1MSAyNS4xNTE5IDE2LjI3NDkgMjQuOTcyNSAxNi41Nzk1IDI1LjA3NDlDMTYuNTM0IDI1LjMyMjUgMTYuNzI5OSAyNS4zNTc4IDE2Ljg4NTQgMjUuNDI5OEMxNi44ODAzIDI1LjU5NzkgMTYuNzgxNyAyNS43Njk3IDE2LjkxMDcgMjUuOTEyNEMxNy4wNjExIDI1Ljc2MDggMTcuMTUwOCAyNS41NDYxIDE3LjM4OTcgMjUuNDgyOUMxOC4xODM1IDI2LjU0MDMgMTguOTkxMSAyNC40MTI5IDIwLjcwODkgMjUuMzcwNUMyMC4zNiAyNS4zNTI4IDIwLjA1MDQgMjUuMzk3IDE5LjgxNTMgMjUuNjgzOEMxOS43NTcxIDI1Ljc0ODIgMTkuNzA3OCAyNS44MjQgMTkuODEwMiAyNS45MDc0QzIwLjczNjcgMjUuMzA5OCAyMC43MzE2IDI2LjExMiAyMS4zMzMzIDI1Ljg2NTdDMjEuNzk1OSAyNS42MjQ0IDIyLjI1NiAyNS4zMjI1IDIyLjgwNTggMjUuNDA4NEMyMi4yNzEyIDI1LjU2MjUgMjIuMjQ5NyAyNS45OTIgMjEuOTM2MiAyNi4zNTQ2QzIxLjg4MzEgMjYuNDEwMSAyMS44NTc4IDI2LjQ3MzMgMjEuOTE5OCAyNi41NjU1QzIzLjAyOTUgMjYuNDcyIDIzLjEyMDUgMjYuMTAzMiAyNC4wMTY3IDI1LjY1MDlDMjQuNjg1MyAyNS4yNDI5IDI1LjM1MTQgMjYuMjMyIDI1LjkzMDMgMjUuNjY4NkMyNi4wNTggMjUuNTQ2MSAyNi4yMzI0IDI1LjU4NzcgMjYuMzkwNCAyNS41NzEzQzI2LjE4ODIgMjQuNDkzNyAyMy45NjQ5IDI1Ljc2ODQgMjQuMDAwMyAyNC4zMjMyQzI0LjcxNTcgMjMuODM2OCAyNC41NTE0IDIyLjkwNTggMjQuNTk5NCAyMi4xNTQxQzI1LjQyMjIgMjIuNjEwMiAyNi4zMzczIDIyLjg3NTUgMjcuMTQzOCAyMy4zMTEzQzI3LjU1MDggMjMuOTY4MiAyOC4xODkxIDI0LjgzNjEgMjkuMDM5NyAyNC43NzkyQzI5LjA2MjUgMjQuNzEzNiAyOS4wODI3IDI0LjY1NTQgMjkuMTA2NyAyNC41ODg1QzI5LjM2NDYgMjQuNjMyNyAyOS42OTU3IDI0LjgwMzIgMjkuODM3MyAyNC40NzczQzMwLjIyMjggMjQuODgwMyAzMC43ODkgMjQuODYwMSAzMS4yOTM0IDI0Ljc1NjVDMzEuNjY2MiAyNC40NTMzIDMwLjU5MTkgMjQuMDIxMyAzMC40NDc4IDIzLjcwOTJMMzAuNDQ5IDIzLjcxMDVaTTUzLjAyNDggMTEuNzEzMUM1My4wMjQ4IDEwLjI0MjcgNTIuNDUzNSA4Ljg2MTkxIDUxLjQxNTggNy44MjQ3NkM1MC4zNzgxIDYuNzg3NjEgNDguOTk2NSA2LjIxNjYgNDcuNTI0IDYuMjE2NkM0Ni4wNTE1IDYuMjE2NiA0NC42NyA2Ljc4NzYxIDQzLjYzMjIgNy44MjQ3Nkw0MS4yNTA5IDEwLjIwNDhDNDAuNjk0OCAxMC43NjA2IDQwLjI3MjYgMTEuNDEzNyAzOS45OTU4IDEyLjE0NTJMMzkuOTc5NCAxMi4xODY5TDM5LjkzNjQgMTIuMTk5NUMzOS4wNzE4IDEyLjQ2NjEgMzguMzA5NyAxMi45MjM0IDM3LjY3MTQgMTMuNTYxM0wzNS4yOSAxNS45NDEzQzMzLjE0NTEgMTguMDg2NCAzMy4xNDUxIDIxLjU3NTYgMzUuMjkgMjMuNzE5NEMzNi4zMjc4IDI0Ljc1NjUgMzcuNzA5MyAyNS4zMjc1IDM5LjE4MDUgMjUuMzI3NUM0MC42NTE4IDI1LjMyNzUgNDIuMDM0NiAyNC43NTY1IDQzLjA3MjMgMjMuNzE5NEw0NS40NTM2IDIxLjMzOTNDNDYuMDA3MiAyMC43ODYgNDYuNDI2OSAyMC4xMzU0IDQ2LjcwMzcgMTkuNDA1M0w0Ni43MjAxIDE5LjM2MzZMNDYuNzYzMSAxOS4zNDk3QzQ3LjYxMjUgMTkuMDg5NCA0OC4zOTYxIDE4LjYxNyA0OS4wMzE5IDE3Ljk4MjhMNTEuNDEzMiAxNS42MDI4QzUyLjQ1MSAxNC41NjU2IDUzLjAyMjMgMTMuMTg0OSA1My4wMjIzIDExLjcxMzFINTMuMDI0OFpNMjEuNzg4MyAyMS45MzA1QzIxLjU4MzYgMjIuNzI4OSAyMS41MTY2IDI0LjA4OTUgMjAuNDc3NiAyNC4xMjg3QzIwLjM5MTYgMjQuNTg5OCAyMC43OTc0IDI0Ljc2MjggMjEuMTY1MiAyNC42MTVDMjEuNTMwNSAyNC40NDcgMjEuNzAzNiAyNC43NDc3IDIxLjgyNjIgMjUuMDQ3MUMyMi4zOSAyNS4xMjkyIDIzLjIyNDIgMjQuODU4OCAyMy4yNTU4IDI0LjE5MThDMjIuNDE0IDIzLjcwNjcgMjIuMTUzNiAyMi43ODQ1IDIxLjc4NzEgMjEuOTMwNUgyMS43ODgzWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMjU5LjM4MSAyNi40Nzk3QzI1Ny43MjUgMjYuNDc5NyAyNTYuMzUgMjYuMTM2NCAyNTUuMjU1IDI1LjQ0OTdDMjU0LjE2IDI0Ljc1NDEgMjUzLjQ4MSAyMy43OTY0IDI1My4yMTkgMjIuNTc2N0wyNTQuMzg2IDIyLjM1OTlDMjU0LjYzIDIzLjI2MzQgMjU1LjIgMjMuOTg2MSAyNTYuMDk2IDI0LjUyODJDMjU3LjAwMSAyNS4wNzAzIDI1OC4xMDUgMjUuMzQxMyAyNTkuNDA4IDI1LjM0MTNDMjYwLjczOCAyNS4zNDEzIDI2MS43OTIgMjUuMDU2NyAyNjIuNTcgMjQuNDg3NkMyNjMuMzU4IDIzLjkxODQgMjYzLjc1MSAyMy4xNDU5IDI2My43NTEgMjIuMTcwMkMyNjMuNzUxIDIxLjYzNzEgMjYzLjYzNCAyMS4yMDM1IDI2My4zOTggMjAuODY5MkMyNjMuMTYzIDIwLjUyNTkgMjYyLjcwMiAyMC4yMTQyIDI2Mi4wMTQgMTkuOTM0MUMyNjEuMzM1IDE5LjY1NCAyNjAuMzMxIDE5LjMzMzMgMjU5LjAwMSAxOC45NzE5QzI1Ny42MDcgMTguNTkyNSAyNTYuNTIxIDE4LjIyNjYgMjU1Ljc0MyAxNy44NzQyQzI1NC45NzQgMTcuNTEyOCAyNTQuNDMxIDE3LjExMDggMjU0LjExNSAxNi42NjgxQzI1My44MDcgMTYuMjE2NCAyNTMuNjUzIDE1LjY2NTMgMjUzLjY1MyAxNS4wMTQ4QzI1My42NTMgMTQuMjM3OCAyNTMuODg0IDEzLjU1MTIgMjU0LjM0NSAxMi45NTQ5QzI1NC44MDcgMTIuMzU4NiAyNTUuNDQ1IDExLjg5MzMgMjU2LjI1OSAxMS41NTlDMjU3LjA3MyAxMS4yMjQ4IDI1OC4wMTQgMTEuMDU3NiAyNTkuMDgyIDExLjA1NzZDMjYwLjE1OSAxMS4wNTc2IDI2MS4xMjcgMTEuMjM4MyAyNjEuOTg3IDExLjU5OTdDMjYyLjg1NSAxMS45NTIgMjYzLjU1MiAxMi40NDg5IDI2NC4wNzcgMTMuMDkwNEMyNjQuNjExIDEzLjcyMjggMjY0LjkxOCAxNC40NTQ2IDI2NSAxNS4yODU4TDI2My44MzMgMTUuNTAyNkMyNjMuNjYxIDE0LjQ4MTcgMjYzLjEzNiAxMy42Nzc3IDI2Mi4yNTggMTMuMDkwNEMyNjEuMzkgMTIuNDk0MSAyNjAuMzA0IDEyLjE5NiAyNTkuMDAxIDEyLjE5NkMyNTcuNzc5IDEyLjE3NzkgMjU2Ljc3OSAxMi40MjY0IDI1Ni4wMDEgMTIuOTQxM0MyNTUuMjMyIDEzLjQ1NjMgMjU0Ljg0NyAxNC4xMjk0IDI1NC44NDcgMTQuOTYwNkMyNTQuODQ3IDE1LjQyMTMgMjU0Ljk3OSAxNS44MTg5IDI1NS4yNDEgMTYuMTUzMUMyNTUuNTAzIDE2LjQ3ODQgMjU1Ljk2IDE2Ljc3NjUgMjU2LjYxMiAxNy4wNDc2QzI1Ny4yNjMgMTcuMzE4NiAyNTguMTY4IDE3LjU5ODcgMjU5LjMyNiAxNy44ODc4QzI2MC43OTIgMTguMjU4MiAyNjEuOTMyIDE4LjYzMzEgMjYyLjc0NyAxOS4wMTI2QzI2My41NyAxOS4zOTIgMjY0LjE0NSAxOS44MzQ3IDI2NC40NzEgMjAuMzQwN0MyNjQuODA1IDIwLjg0NjYgMjY0Ljk3MyAyMS40NzQ1IDI2NC45NzMgMjIuMjI0NEMyNjQuOTczIDIzLjU1MjUgMjY0LjQ3NSAyNC41OTYgMjYzLjQ4IDI1LjM1NDlDMjYyLjQ4NCAyNi4xMDQ3IDI2MS4xMTggMjYuNDc5NyAyNTkuMzgxIDI2LjQ3OTdaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yNDUuMjkxIDI2LjUwNjhDMjQzLjgzNCAyNi41MDY4IDI0Mi42MTMgMjYuMTgxNSAyNDEuNjI2IDI1LjUzMUMyNDAuNjQgMjQuODgwNiAyMzkuODkzIDIzLjk3NzEgMjM5LjM4NyAyMi44MjA3QzIzOC44OCAyMS42NTUyIDIzOC42MTMgMjAuMzA5IDIzOC41ODYgMTguNzgyMkMyMzguNjEzIDE3LjIxOTIgMjM4Ljg4IDE1Ljg1OTUgMjM5LjM4NyAxNC43MDMxQzIzOS45MDIgMTMuNTQ2NiAyNDAuNjU0IDEyLjY1MjIgMjQxLjY0IDEyLjAxOThDMjQyLjYyNiAxMS4zNzgzIDI0My44NDMgMTEuMDU3NiAyNDUuMjkxIDExLjA1NzZDMjQ2LjY0OCAxMS4wNTc2IDI0Ny44NTYgMTEuMzgyOSAyNDguOTE1IDEyLjAzMzRDMjQ5Ljk4MyAxMi42NzQ4IDI1MC43MzggMTMuNTYwMiAyNTEuMTgxIDE0LjY4OTVMMjUwLjA5NiAxNS4xNTAzQzI0OS42ODggMTQuMjEwNyAyNDkuMDYgMTMuNDgzNCAyNDguMjA5IDEyLjk2ODRDMjQ3LjM2OCAxMi40NTM1IDI0Ni4zOTUgMTIuMTk2IDI0NS4yOTEgMTIuMTk2QzI0NC4wNiAxMi4xOTYgMjQzLjA0MiAxMi40NzYgMjQyLjIzNyAxMy4wMzYyQzI0MS40MzIgMTMuNTg3MyAyNDAuODMgMTQuMzU5OCAyNDAuNDMyIDE1LjM1MzZDMjQwLjAzNCAxNi4zMzgzIDIzOS44MjYgMTcuNDgxMiAyMzkuODA3IDE4Ljc4MjJDMjM5LjgzNSAyMC43Njk4IDI0MC4zMDUgMjIuMzY0NCAyNDEuMjE5IDIzLjU2NkMyNDIuMTMzIDI0Ljc2NzYgMjQzLjQ5IDI1LjM2ODQgMjQ1LjI5MSAyNS4zNjg0QzI0Ni4zNjggMjUuMzY4NCAyNDcuMzIyIDI1LjEyIDI0OC4xNTUgMjQuNjIzMUMyNDguOTg3IDI0LjEyNjIgMjQ5LjYyNSAyMy4zOTg5IDI1MC4wNjggMjIuNDQxMkwyNTEuMTgxIDIyLjkyOTFDMjUwLjU3NSAyNC4xMDM2IDI0OS43NzQgMjQuOTkzNSAyNDguNzc5IDI1LjU5ODhDMjQ3Ljc4NCAyNi4yMDQxIDI0Ni42MjEgMjYuNTA2OCAyNDUuMjkxIDI2LjUwNjhaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yMjkuNzAzIDI2LjUwNjhDMjI4LjI1NSAyNi41MDY4IDIyNy4wMzQgMjYuMTc3IDIyNi4wMzggMjUuNTE3NUMyMjUuMDQzIDI0Ljg1OCAyMjQuMjg3IDIzLjk0NTUgMjIzLjc3MiAyMi43OEMyMjMuMjU2IDIxLjYxNDUgMjIyLjk5OCAyMC4yNzI5IDIyMi45OTggMTguNzU1MUMyMjIuOTk4IDE3LjIxOTIgMjIzLjI2IDE1Ljg3MzEgMjIzLjc4NSAxNC43MTY2QzIyNC4zMSAxMy41NjAyIDIyNS4wNyAxMi42NjEzIDIyNi4wNjUgMTIuMDE5OEMyMjcuMDcgMTEuMzc4MyAyMjguMjgyIDExLjA1NzYgMjI5LjcwMyAxMS4wNTc2QzIzMS4xNiAxMS4wNTc2IDIzMi4zODYgMTEuMzg3NCAyMzMuMzgxIDEyLjA0NjlDMjM0LjM3NyAxMi42OTc0IDIzNS4xMjggMTMuNjAwOSAyMzUuNjM0IDE0Ljc1NzNDMjM2LjE1IDE1LjkxMzcgMjM2LjQwOCAxNy4yNDYzIDIzNi40MDggMTguNzU1MUMyMzYuNDA4IDIwLjMgMjM2LjE1IDIxLjY1NTIgMjM1LjYzNCAyMi44MjA3QzIzNS4xMTkgMjMuOTc3MSAyMzQuMzU4IDI0Ljg4MDYgMjMzLjM1NCAyNS41MzFDMjMyLjM1OSAyNi4xODE1IDIzMS4xNDIgMjYuNTA2OCAyMjkuNzAzIDI2LjUwNjhaTTIyOS43MDMgMjUuMzY4NEMyMzEuNTQ5IDI1LjM2ODQgMjMyLjkyNCAyNC43NTg2IDIzMy44MjkgMjMuNTM4OUMyMzQuNzM0IDIyLjMxMDIgMjM1LjE4NiAyMC43MTU2IDIzNS4xODYgMTguNzU1MUMyMzUuMTg2IDE2Ljc1ODUgMjM0LjcyOSAxNS4xNjg0IDIzMy44MTYgMTMuOTg0OEMyMzIuOTExIDEyLjc5MjMgMjMxLjU0IDEyLjE5NiAyMjkuNzAzIDEyLjE5NkMyMjguNDYzIDEyLjE5NiAyMjcuNDM2IDEyLjQ3NiAyMjYuNjIyIDEzLjAzNjJDMjI1LjgxNyAxMy41OTYzIDIyNS4yMTUgMTQuMzY4OCAyMjQuODE3IDE1LjM1MzZDMjI0LjQxOSAxNi4zMzgzIDIyNC4yMiAxNy40NzIyIDIyNC4yMiAxOC43NTUxQzIyNC4yMiAyMC43NDI3IDIyNC42ODEgMjIuMzQxOCAyMjUuNjA0IDIzLjU1MjVDMjI2LjUzNiAyNC43NjMxIDIyNy45MDIgMjUuMzY4NCAyMjkuNzAzIDI1LjM2ODRaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0yMDYuMTA0IDI2LjEwMDJWNi41ODU0NUgyMTEuODMyQzIxMi4wNjcgNi41ODU0NSAyMTIuNDQzIDYuNTg5OTcgMjEyLjk1OSA2LjU5OUMyMTMuNDc1IDYuNjA4MDQgMjEzLjk2OCA2LjY0ODY5IDIxNC40MzggNi43MjA5N0MyMTUuODc3IDYuOTI4NzYgMjE3LjA2NyA3LjQ3OTg3IDIxOC4wMDggOC4zNzQzQzIxOC45NTggOS4yNjg3MiAyMTkuNjY0IDEwLjQwNzEgMjIwLjEyNSAxMS43ODk0QzIyMC41ODcgMTMuMTYyNiAyMjAuODE3IDE0LjY4MDUgMjIwLjgxNyAxNi4zNDI4QzIyMC44MTcgMTguMDE0MiAyMjAuNTg3IDE5LjU0MTEgMjIwLjEyNSAyMC45MjM0QzIxOS42NjQgMjIuMjk2NiAyMTguOTU4IDIzLjQzMDUgMjE4LjAwOCAyNC4zMjQ5QzIxNy4wNjcgMjUuMjEwMyAyMTUuODc3IDI1Ljc1NjkgMjE0LjQzOCAyNS45NjQ3QzIxMy45NzcgMjYuMDI3OSAyMTMuNDc5IDI2LjA2ODYgMjEyLjk0NSAyNi4wODY2QzIxMi40MiAyNi4wOTU3IDIxMi4wNDkgMjYuMTAwMiAyMTEuODMyIDI2LjEwMDJIMjA2LjEwNFpNMjA3LjMyNiAyNC45NjE4SDIxMS44MzJDMjEyLjI2NyAyNC45NjE4IDIxMi43MDEgMjQuOTQ4MyAyMTMuMTM1IDI0LjkyMTJDMjEzLjU3OSAyNC44OTQxIDIxMy45NSAyNC44NTM0IDIxNC4yNDggMjQuNzk5MkMyMTUuNTMzIDI0LjU4MjQgMjE2LjU2NSAyNC4wOSAyMTcuMzQzIDIzLjMyMkMyMTguMTMgMjIuNTQ1MSAyMTguNyAyMS41NjAzIDIxOS4wNTMgMjAuMzY3N0MyMTkuNDE1IDE5LjE2NjEgMjE5LjU5NiAxNy44MjQ1IDIxOS41OTYgMTYuMzQyOEMyMTkuNTk2IDE0Ljg2MTEgMjE5LjQxNSAxMy41MjQgMjE5LjA1MyAxMi4zMzE1QzIxOC43IDExLjEyOTkgMjE4LjEzIDEwLjE0NTEgMjE3LjM0MyA5LjM3NzE0QzIxNi41NjUgOC42MDAxNiAyMTUuNTMzIDguMTAzMjYgMjE0LjI0OCA3Ljg4NjQzQzIxMy45NSA3LjgzMjIyIDIxMy41NzQgNy43OTE1NyAyMTMuMTIyIDcuNzY0NDZDMjEyLjY2OSA3LjczNzM2IDIxMi4yMzkgNy43MjM4MSAyMTEuODMyIDcuNzIzODFIMjA3LjMyNlYyNC45NjE4WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNNzQuNDMwNyA3LjA3ODEyVjI2LjIyOTVIODcuNjMwM1YyMy4zMzc4SDc3LjQyNzVWNy4wNzgxMkg3NC40MzA3WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTQxLjQ4NCA3LjA3ODEyQzEzOC44ODkgNy4wNzgxMiAxMzYuNjg3IDguMDEyOTUgMTM1LjExNiA5Ljc4MjgxQzEzMy41NTkgMTEuNTM2MiAxMzIuNzM3IDEzLjk5NzEgMTMyLjczNyAxNi44OTg5QzEzMi43MzcgMjIuODY1MyAxMzYuMTgyIDI2LjcyMDkgMTQxLjUxMSAyNi43MjA5QzE0NS4yNjYgMjYuNzIwOSAxNDguMTczIDI0Ljc1NzcgMTQ5LjI4OSAyMS40NzA3TDE0OS41NTkgMjAuNjczNUwxNDYuNTg1IDE5LjU0NDJMMTQ2LjMxMSAyMC40MzIzQzE0NS42NDYgMjIuNTgxMSAxNDMuOTQxIDIzLjc2NDggMTQxLjUwOSAyMy43NjQ4QzEzOC4wMzYgMjMuNzY0OCAxMzUuODc4IDIxLjEzNDYgMTM1Ljg3OCAxNi45MDAxQzEzNS44NzggMTIuNjY1NiAxMzguMDU2IDEwLjAzNTUgMTQxLjU2MiAxMC4wMzU1QzE0My45OTMgMTAuMDM1NSAxNDUuMzkzIDEwLjk4OCAxNDYuMTA2IDEzLjEyMjlMMTQ2LjQxNyAxNC4wNTRMMTQ5LjMxMyAxMi42OTU5TDE0OS4wNDggMTEuOTUwNkMxNDcuOTE1IDguNzY0NiAxNDUuMyA3LjA3OTM5IDE0MS40ODMgNy4wNzkzOUwxNDEuNDg0IDcuMDc4MTJaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik05NC42NjU1IDExLjYyMzVDOTEuNzg4NyAxMS42MjM1IDg5LjYzNzQgMTIuOTcxNSA4OC43NjQgMTUuMzIxMkM4OC43MDg0IDE1LjQ3MTUgODguNTQwMyAxNS45MjUgODguNTQwMyAxNS45MjVMOTEuMDA2MyAxNy41MTkzTDkxLjM0MTMgMTYuNjQ2M0M5MS45MTI2IDE1LjE1ODIgOTIuOTY5MyAxNC40NjQ3IDk0LjY2NTUgMTQuNDY0N0M5Ni4zNjE4IDE0LjQ2NDcgOTcuMzMyNSAxNS4yODcgOTcuMzE0OCAxNi45MDY2Qzk3LjMxNDggMTYuOTcyMyA5Ny4zMDk3IDE3LjE3MDYgOTcuMzA5NyAxNy4xNzA2Qzk3LjMwOTcgMTcuMTcwNiA5NS4wNjQ5IDE3LjUzNDQgOTQuMTM5NyAxNy43MzAyQzkwLjE5MjMgMTguNTY0IDg4LjUzOTEgMjAuMDY5OCA4OC41MzkxIDIyLjUzMzJDODguNTM5MSAyMy44NDU4IDg5LjI2ODQgMjUuMjY3IDkwLjU5OTMgMjYuMDY0MUM5MS4zOTgyIDI2LjU0MTYgOTIuNDQwOSAyNi43MjIzIDkzLjU5MjQgMjYuNzIyM0M5NC4zNDk1IDI2LjcyMjMgOTUuMDg1MiAyNi42MDk4IDk1Ljc2NjQgMjYuNDAyNkM5Ny4zMTQ4IDI1Ljg4ODUgOTcuNzQ3MSAyNC44Nzc5IDk3Ljc0NzEgMjQuODc3OVYyNi4xOTkzSDEwMC4zMTJWMTYuNzUyNUMxMDAuMzEyIDEzLjU0MTIgOTguMjAwOCAxMS42MjM1IDk0LjY2NTUgMTEuNjIzNVpNOTcuMzIzNyAyMS43MDQ1Qzk3LjMyMzcgMjIuNjk3NCA5Ni4yNDE3IDI0LjA5NTkgOTMuNzIxMyAyNC4wOTU5QzkzLjAwOTcgMjQuMDk1OSA5Mi41MDU0IDIzLjkwNzcgOTIuMTY5MiAyMy42MjcyQzkxLjcxOTIgMjMuMjUyIDkxLjU3MTMgMjIuNzEyNiA5MS42MzMzIDIyLjIzNjRDOTEuNjU5OCAyMi4wMjkyIDkxLjc4NDkgMjEuNTgzMiA5Mi4yNDg4IDIxLjE5NjdDOTIuNzIyOCAyMC44MDEzIDkzLjU2MDggMjAuNTE4MyA5NC44NTUxIDIwLjIzNjZDOTUuOTE5NCAyMC4wMDU0IDk3LjMyNDkgMTkuNzUwMiA5Ny4zMjQ5IDE5Ljc1MDJWMjEuNzA1OEw5Ny4zMjM3IDIxLjcwNDVaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0xMDkuNzkzIDExLjYyMjFDMTA5LjQzNyAxMS42MjIxIDEwOS4wODkgMTEuNjQ3MyAxMDguNzUyIDExLjY5NDFDMTA2LjQ1NSAxMi4wMzkgMTA1Ljc4MyAxMy4yMDUgMTA1Ljc4MyAxMy4yMDVMMTA1Ljc4NSAxMi4wMjg4SDEwMi45MTFWMjYuMjAxNkgxMDUuOTA4VjE4LjM0NjVDMTA1LjkwOCAxNS42NzcyIDEwNy44NTYgMTQuNDYxOSAxMDkuNjY2IDE0LjQ2MTlDMTExLjYyMiAxNC40NjE5IDExMi41NzMgMTUuNTEzIDExMi41NzMgMTcuNjc3VjI2LjIwMTZIMTE1LjU3VjE3LjI2NTFDMTE1LjU3IDEzLjc4MzUgMTEzLjM1NyAxMS42MjIxIDEwOS43OTUgMTEuNjIyMUgxMDkuNzkzWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTkzLjU5NiAxMS42MjIxQzE5My4yNCAxMS42MjIxIDE5Mi44OTIgMTEuNjQ3MyAxOTIuNTU1IDExLjY5NDFDMTkwLjI1OCAxMi4wMzkgMTg5LjU4NiAxMy4yMDUgMTg5LjU4NiAxMy4yMDVWMTIuMDI3NkgxODYuNzE0VjI2LjIwMTZIMTg5LjcxMVYxOC4zNDY1QzE4OS43MTEgMTUuNjc3MiAxOTEuNjU5IDE0LjQ2MTkgMTkzLjQ2OSAxNC40NjE5QzE5NS40MjUgMTQuNDYxOSAxOTYuMzc2IDE1LjUxMyAxOTYuMzc2IDE3LjY3N1YyNi4yMDE2SDE5OS4zNzNWMTcuMjY1MUMxOTkuMzczIDEzLjc4MzUgMTk3LjE1OSAxMS42MjIxIDE5My41OTcgMTEuNjIyMUgxOTMuNTk2WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTI4LjA3NiAxMi4wMjg4VjEzLjQ4NzlDMTI4LjA3NiAxMy40ODc5IDEyNy4zNDIgMTEuNjIyMSAxMjQuMDAxIDExLjYyMjFDMTE5Ljg1IDExLjYyMjEgMTE3LjI3MSAxNC40ODQ3IDExNy4yNzEgMTkuMDk0NEMxMTcuMjcxIDIxLjY5NTUgMTE4LjEwMyAyMy43NDMyIDExOS41NzEgMjUuMDM2OEMxMjAuNzEyIDI2LjA0MjQgMTIyLjIzNiAyNi41NTc4IDEyNC4wNTEgMjYuNTkzMkMxMjUuMzE0IDI2LjYxNzIgMTI2LjEzMiAyNi4yNzM2IDEyNi42NDMgMjUuOTQ4OUMxMjcuNjIzIDI1LjMyNDkgMTI3Ljk4NyAyNC43MzI0IDEyNy45ODcgMjQuNzMyNEMxMjcuOTg3IDI0LjczMjQgMTI3Ljk0NiAyNS4xOTYgMTI3Ljg3IDI1LjgyMzlDMTI3LjgxNiAyNi4yNzg2IDEyNy43MTMgMjYuNTk4MyAxMjcuNzEzIDI2LjU5ODNDMTI3LjI1NyAyOC4yMjE2IDEyNS45MjIgMjkuMTYwMiAxMjMuOTc2IDI5LjE2MDJDMTIyLjAyOSAyOS4xNjAyIDEyMC44NSAyOC41MTk3IDEyMC42MTYgMjcuMjU3N0wxMTcuNzAyIDI4LjEyNjhDMTE4LjIwNiAzMC41NTIzIDEyMC40ODMgMzIgMTIzLjc5NSAzMkMxMjYuMDQ2IDMyIDEyNy44MSAzMS4zODg2IDEyOS4wNCAzMC4xODA5QzEzMC4yOCAyOC45NjMxIDEzMC45MSAyNy4yMDg0IDEzMC45MSAyNC45NjQ4VjEyLjAyNzZIMTI4LjA3NlYxMi4wMjg4Wk0xMjcuODg2IDE5LjIyMzJDMTI3Ljg4NiAyMi4wNTggMTI2LjUwMSAyMy43NTA4IDEyNC4xOCAyMy43NTA4QzEyMS42OTQgMjMuNzUwOCAxMjAuMjY4IDIyLjA1MyAxMjAuMjY4IDE5LjA5NDRDMTIwLjI2OCAxNi4xMzU4IDEyMS42OTQgMTQuNDYzMiAxMjQuMTggMTQuNDYzMkMxMjYuNDQ1IDE0LjQ2MzIgMTI3Ljg2NSAxNi4xNDg0IDEyNy44ODYgMTguODYxOVYxOS4yMjMyWiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTU4LjE5MiAxMS42MjIxQzE1Ny44NjMgMTEuNjIyMSAxNTcuNTQzIDExLjY0MzYgMTU3LjIzMyAxMS42ODRDMTU0Ljk3MyAxMi4wMzY1IDE1NC4zMDggMTMuMTg3MyAxNTQuMzA4IDEzLjE4NzNWMTIuODUwMUgxNTQuMzA2VjcuMDc4MTJIMTUxLjMxVjI2LjIwMjlIMTU0LjMwNlYxOC4zNDc4QzE1NC4zMDYgMTUuNjYwOSAxNTYuMjU0IDE0LjQzOCAxNTguMDY0IDE0LjQzOEMxNjAuMDIxIDE0LjQzOCAxNjAuOTcxIDE1LjQ4OSAxNjAuOTcxIDE3LjY1M1YyNi4yMDI5SDE2My45NjhWMTcuMjQxMkMxNjMuOTY4IDEzLjgyOTEgMTYxLjcwMSAxMS42MjM0IDE1OC4xOTMgMTEuNjIzNEwxNTguMTkyIDExLjYyMjFaIiBmaWxsPSIjMUMzQzNDIi8+CjxwYXRoIGQ9Ik0xODIuNDQ4IDEwLjk2NTRDMTgzLjUyMSAxMC45NjU0IDE4NC4zOSAxMC4wOTYgMTg0LjM5IDkuMDIzNjlDMTg0LjM5IDcuOTUxMzQgMTgzLjUyMSA3LjA4MjAzIDE4Mi40NDggNy4wODIwM0MxODEuMzc1IDcuMDgyMDMgMTgwLjUwNSA3Ljk1MTM0IDE4MC41MDUgOS4wMjM2OUMxODAuNTA1IDEwLjA5NiAxODEuMzc1IDEwLjk2NTQgMTgyLjQ0OCAxMC45NjU0WiIgZmlsbD0iIzFDM0MzQyIvPgo8cGF0aCBkPSJNMTgwLjk1OCAxMi4wMjE1VjE5LjIxNDZDMTgwLjEwNSAxOC41MTIyIDE3OS4xMTIgMTcuOTgyOSAxNzcuOTg3IDE3LjY2NThWMTYuNzUyNUMxNzcuOTg3IDEzLjU0MTIgMTc1Ljg3NyAxMS42MjM1IDE3Mi4zNDEgMTEuNjIzNUMxNjkuNDY1IDExLjYyMzUgMTY3LjMxMyAxMi45NzE1IDE2Ni40NCAxNS4zMjEyQzE2Ni4zODQgMTUuNDcxNSAxNjYuMjE2IDE1LjkyNSAxNjYuMjE2IDE1LjkyNUwxNjguNjgyIDE3LjUxOTNMMTY5LjAxNyAxNi42NDYzQzE2OS41ODggMTUuMTU4MiAxNzAuNjQ1IDE0LjQ2NDcgMTcyLjM0MSAxNC40NjQ3QzE3NC4wMzggMTQuNDY0NyAxNzUuMDA4IDE1LjI4NyAxNzQuOTkxIDE2LjkwNjZDMTc0Ljk5MSAxNi45MTY3IDE3NC45OTEgMTcuMDUxOCAxNzQuOTkxIDE3LjI2NzlDMTczLjcyMiAxNy4yMzI1IDE3Mi41NDEgMTcuMzU1IDE3MS40ODEgMTcuNjAzOUMxNzAuMDgzIDE3LjkxOTcgMTY3LjQ4NiAxOC43MjE5IDE2Ni41NTkgMjAuODA3NkMxNjYuNTUyIDIwLjgyMTUgMTY2LjQxNiAyMS4xODE1IDE2Ni40MTYgMjEuMTgxNUMxNjYuMjgyIDIxLjU5NTkgMTY2LjIxNSAyMi4wNDU2IDE2Ni4yMTUgMjIuNTMzMkMxNjYuMjE1IDIzLjg0NTggMTY2Ljk0NCAyNS4yNjcgMTY4LjI3NSAyNi4wNjQxQzE2OS4wNzQgMjYuNTQxNiAxNzAuMTE3IDI2LjcyMjMgMTcxLjI2OCAyNi43MjIzQzE3Mi4wMTEgMjYuNzIyMyAxNzIuNzM0IDI2LjYxMzYgMTczLjQwNiAyNi40MTRDMTc0Ljk4NCAyNS45MDM3IDE3NS40MjMgMjQuODc3OSAxNzUuNDIzIDI0Ljg3NzlWMjYuMjAwNUgxNzcuOTg3VjIxLjg3MTNDMTc3LjI2NyAyMS40MjE1IDE3Ni4xODUgMjEuMTU2MiAxNzQuOTk4IDIxLjE1ODhDMTc0Ljk5OCAyMS40OTM1IDE3NC45OTggMjEuNzA1OCAxNzQuOTk4IDIxLjcwNThDMTc0Ljk5OCAyMi42OTg3IDE3My45MTYgMjQuMDk3MiAxNzEuMzk2IDI0LjA5NzJDMTcwLjY4NCAyNC4wOTcyIDE3MC4xOCAyMy45MDg5IDE2OS44NDQgMjMuNjI4NUMxNjkuMzk0IDIzLjI1MzMgMTY5LjI0NiAyMi43MTM5IDE2OS4zMDggMjIuMjM3NkMxNjkuMzM0IDIyLjAzMDQgMTY5LjQ1OSAyMS41ODQ1IDE2OS45MjMgMjEuMTk3OUwxNjkuOTE4IDIxLjE4NEMxNzAuOTgzIDIwLjMxMzYgMTczLjA3NCAxOS45NjYyIDE3NC45OTYgMjAuMDQyVjIwLjA0NThDMTc2LjYzMSAyMC4xMDUyIDE3Ny44NTUgMjAuNDI2MSAxNzguNzI4IDIxLjAyNzRDMTc4Ljk2NiAyMS4xNzc3IDE3OS4xODkgMjEuMzQ1NyAxNzkuMzk2IDIxLjUzMDJDMTgwLjI3MyAyMi4zMTcyIDE4MC42MjUgMjMuMjg2MSAxODAuNzc3IDIzLjg1MjFDMTgxLjAyNCAyNC43NzU1IDE4MC45NTggMjYuMTk4IDE4MC45NTggMjYuMTk4SDE4My45MzlWMTIuMDI0SDE4MC45NThWMTIuMDIxNVoiIGZpbGw9IiMxQzNDM0MiLz4KPC9zdmc+){.nav-logo .w-auto .relative .object-contain .block .dark:hidden .max-w-48 .h-[26px]}![dark logo](data:,){.nav-logo .w-auto .relative .object-contain .hidden .dark:block .max-w-48 .h-[26px] .sf-hidden}](https://docs.langchain.com/)

::: {.flex .gap-4 .min-w-[140px] .max-w-[492px] .flex-wrap .h-fit .md:hidden .justify-end .sf-hidden}
:::
:::

::: {.flex .flex-col .sm:grid .max-md:!grid-cols-2 .gap-8 .flex-1 style="grid-template-columns:repeat(2,minmax(0px,1fr))"}
::: {.flex .flex-col .gap-4 .flex-1 .whitespace-nowrap .w-full .md:items-center}
::: {.flex .gap-4 .flex-col}
Resources

[Forum](https://forum.langchain.com/){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}[Changelog](https://changelog.langchain.com/){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}[LangChain Academy](https://academy.langchain.com/){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}[Trust Center](https://trust.langchain.com/){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}
:::
:::

::: {.flex .flex-col .gap-4 .flex-1 .whitespace-nowrap .w-full .md:items-center}
::: {.flex .gap-4 .flex-col}
Company

[About](https://langchain.com/about){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}[Careers](https://langchain.com/careers){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}[Blog](https://blog.langchain.com/){.text-sm .max-w-36 .whitespace-normal .md:truncate .text-gray-950/50 .dark:text-white/50 .hover:text-gray-950/70 .dark:hover:text-white/70}
:::
:::
:::

::: {.gap-4 .min-w-[140px] .max-w-[492px] .flex-wrap .hidden .md:flex .justify-end}
[github]{.sr-only}

[x]{.sr-only}

[linkedin]{.sr-only}

[youtube]{.sr-only}
:::
:::

::: {.h-[1px] .w-full .bg-gray-100 .dark:bg-white/5}
:::

::: {.flex .items-center .justify-between}
::: {.sm:flex}
[Powered by Mintlify](https://www.mintlify.com/?utm_campaign=poweredBy&utm_medium=referral&utm_source=langchain-5e9cc07a){.text-sm .text-gray-500 .dark:text-gray-400 .hover:text-gray-700 .dark:hover:text-gray-300}
:::

::: {.flex .items-center .gap-2}
:::
:::
:::
:::
:::
:::

::: {#host-style-container}
:::

::: {#ciciai-shadow-container .cici-ext-container style="z-index:2147483647;position:absolute;top:0px;left:0px;visibility:visible"}
::: {.assistant-WN6uj2 .cici-ext-always-light .semi-always-light}
::: {.floatBtn-nYCoit .right-mFtx7v style="transform:translate3d(0px,-436.363px,0px)"}
::: {.floatBtnWrapper-zCbk0E .reverse-rlMQSO}
::: {style="width:40px;display:flex;justify-content:end"}
::: {.floatBtnList-aSPWo7 .sf-hidden data-role="float-button-list" style="flex-direction:column-reverse"}
:::
:::

::: {.floatBtnBrand-zSQfek data-testid="float-button-brand-entry"}
::: {.closeBtn-npVDT3 data-testid="disable-option"}
:::

![](data:,){.floatBtnAvatar-W7l5QB}
:::
:::
:::

::: {.cici-popup-container}
:::
:::
:::

::: {#doubao-ai-translate-image-assistante86239fa-724d-47d7-a29e-c85f1fd34d0b data-collection-img-host-id="e86239fa-724d-47d7-a29e-c85f1fd34d0b"}
::: {#host-style-container}
:::
:::

::: {style="width:0px;height:0px;position:absolute;z-index:200000"}
::: {#host-style-container}
:::

::: {.cici-ext-container .semi-always-light .cici-ext-always-light}
:::
:::

::: {#doubao-ai-assistant .flow-ai-select-bar-enabled .flow-ai-select-bar-support-iframe aria-label="flow-ai-assistant" aria-description="flow-ai-select-bar-enabled flow-ai-select-bar-support-iframe" style="width:0px;height:0px;position:absolute;top:0px;left:0px;overflow:hidden"}
:::

::: {#__next-route-announcer__ aria-live="assertive" role="alert" style="position:absolute;border:0px;height:1px;margin:-1px;padding:0px;width:1px;clip:rect(0px,0px,0px,0px);overflow:hidden;white-space:nowrap;overflow-wrap:normal"}
Deep Agents overview - Docs by LangChain
:::

::: {.z-20 .fixed .right-0 .w-[23rem] .border-l .border-gray-500/5 .dark:border-gray-300/[0.06] .bg-background-light .dark:bg-background-dark .h-[calc(100vh-9.5rem)] .top-[9.5rem] .transition-[width] .duration-300 .ease-in-out .invisible style="width:368px;min-width:368px;max-width:576px"}
::: {.absolute .-left-1 .top-0 .bottom-0 .w-1 .hover:bg-gray-200/70 .dark:hover:bg-white/[0.07] .z-10 .cursor-col-resize .after:content-[""] .after:absolute .after:inset-[-8px] .after:select-none}
:::

::: {#chat-assistant-sheet .flex .flex-col .overflow-hidden .shrink-0 .absolute .inset-0 .-top-px .min-h-full .transition-transform .duration-200 .ease-out .chat-assistant-sheet aria-hidden="true"}
::: {.w-full .flex .flex-col .pb-4 .h-full .lg:pt-3}
::: {.chat-assistant-sheet-header .flex .items-center .justify-between .pb-3 .px-4}
::: {.flex .items-center .gap-2}
[Assistant]{.font-semibold .text-gray-900 .dark:text-gray-100}
:::

::: {.flex .items-center .gap-1}
:::
:::

::: {#chat-content .chat-assistant-sheet-content .flex-1 .overflow-y-auto .relative .px-4}
::: {.h-full .flex .flex-col .justify-between}
::: {.mt-4 .flex .flex-col .items-center .text-sm}
::: {.mx-8 .text-center .text-gray-400 .dark:text-gray-600 .text-xs .chat-assistant-disclaimer-text}
Responses are generated using AI and may contain mistakes.
:::
:::
:::
:::

::: {.px-4}
<div>

::: {.flex .flex-col .w-full .bg-background-light .dark:bg-background-dark .border .border-gray-200 .dark:border-gray-600/30 .rounded-2xl .has-[textarea:focus]:border-primary .dark:has-[textarea:focus]:border-primary-light}
::: {.relative .flex .items-end}
:::
:::

</div>
:::
:::
:::
:::

x

::: {#auvsv7cw}
::: {style="height:100vh;width:100vw;position:fixed;left:-10000px;visibility:hidden"}
:::
:::

::: {#__yetone-nextai-translator style="z-index:2147483647"}
<div>

::: {#__yetone-nextai-translator-popup-thumb data-text="spawning" style="position:absolute;z-index:2147483647;background:rgb(255,255,255);padding:2px;border-radius:4px;box-shadow:rgba(0,0,0,0.2) 0px 0px 4px;cursor:pointer;user-select:none;width:20px;height:20px;overflow:hidden;visibility:hidden;opacity:100;left:747px;top:1340px"}
![](data:,)
:::

</div>
:::
