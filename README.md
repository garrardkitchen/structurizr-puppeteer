# Structurizr Puppeteer

This repo contains some Node.js examples of how to script and automate parts of Structurizr Lite/on-premises/cloud service using Puppeteer (and headless Chrome) from the command line, perhaps as a part of your build process.

The command line examples that follow assume that you have [Node.js](https://nodejs.org) and [Puppeteer](https://developers.google.com/web/tools/puppeteer/) installed.

## Exporting diagrams

```
node export-diagrams.js <diagram page URL> <png|svg> [username] [password]
```

## To Get Started

**Step 1** - start structurizr/lite

```powershell
docker run -it --rm -p 8080:8080 -v $PWD/workspace:/usr/local/structurizr structurizr/lite
```

**Step 2** - download repo

```powershell
git clone https://github.com/garrardkitchen/structurizr-puppeteer.git
cd structurizr-puppeteer
npm install puppeteer
```

**Step 3** - export PNGs

```powershell
node export-diagrams.js http://localhost:8080/workspace/diagrams png
```

---

### Examples

Structurizr Lite:

```
node export-diagrams.js http://localhost:8080/workspace/diagrams png
```

Unauthenticated access to diagrams on the cloud service:

```
node export-diagrams.js https://structurizr.com/share/36141/diagrams png
```

Authenticated access to diagrams on an on-premises installation

```
node export-diagrams.js http://localhost:8080/workspace/1/diagrams png username password
```

## Exporting documentation

```
node export-documentation.js <documentation page URL> [username] [password]
```

### Examples

Structurizr Lite (workspace or default documentation):

```
node export-documentation.js http://localhost:8080/workspace/documentation
```

Unauthenticated access to documentation on the cloud service (specific software system documentation):

```
node export-documentation.js https://structurizr.com/share/31/documentation/Financial%20Risk%20System
```

Authenticated access to documentation on an on-premises installation (workspace or default documentation):

```
node export-documentation.js http://localhost:8080/workspace/1/documentation username password
```
