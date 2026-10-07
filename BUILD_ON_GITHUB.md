# One Piece: Grand Line — build on GitHub (Linux)

This project targets **Minecraft 1.21.1 + NeoForge 21.1.235 + Java 21**.

You do **not** need Gradle installed on your Chromebook/Linux system for the GitHub method. GitHub Actions installs Java and Gradle for the build.

## Method A — easiest: GitHub website

1. Go to https://github.com/ and sign in.
2. Click **+** → **New repository**.
3. Name it something like `grandline`.
4. Create the repository. A README is not required.
5. Download/extract this project. Open the `grandline` folder from the ZIP.
6. On GitHub, open your new repository and choose **Add file → Upload files**.
7. Upload the **contents of the `grandline` folder**, not the outer `grandline` folder itself. At the top level you should see `build.gradle`, `gradle.properties`, `settings.gradle`, `src`, `.github`, and `tools`.
8. Click **Commit changes**.
9. Open the **Actions** tab. You should see **Build One Piece Grand Line** running automatically.
10. Open the completed run. Scroll to **Artifacts**.
11. Download `grandline-jar` for the playable mod JAR, or `grandline-mrpack` for the Modrinth pack.

## Method B — terminal + Git

First create an empty GitHub repository in your browser, then run:

```bash
git clone https://github.com/YOUR_USERNAME/grandline.git
cd grandline
```

Copy the **contents** of the project's `grandline` folder into this directory. Then:

```bash
git add .
git commit -m "Add One Piece Grand Line mod"
git push origin main
```

GitHub Actions will build it automatically. You can then use the **Actions** tab to download the JAR or `.mrpack` artifact.

## Installing the JAR in Minecraft

For a normal NeoForge instance:

```text
Minecraft 1.21.1
NeoForge 21.1.235
Java 21
```

Put the built `grandline-0.5.0.jar` into the instance's `mods` folder.

## Installing the .mrpack

In Modrinth App, create/import an instance from the `.mrpack` file. The pack declares Minecraft 1.21.1 and NeoForge 21.1.235 and places the Grand Line mod in the instance's `mods` folder.

## Creator/testing commands

After entering a singleplayer world, the project docs include Creator commands such as:

```text
/onepiece fruit give leopard
/onepiece mastery max
/onepiece haki unlock all
/onepiece haki infinite
/onepiece stamina infinite
/onepiece cooldown reset
```

The full list is in `docs/CONTROLS_AND_COMMANDS.md`.

## If the GitHub Action fails

Open the failed workflow run → the failed step → copy the error text. The useful information is the first actual Gradle/Java compilation error; warnings above it usually are not the cause.
