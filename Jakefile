const fs = require("fs-extra");
const path = require("path");
const ejs = require("ejs");

const dockerfile = /([a-z]+)-(latest|[0-9]+)-([a-z]+)\/Dockerfile/;

const FROM = {
  alpine: (version) => version === "latest" ? "alpine" : `node:${version}-alpine`,
  jessie: (version) => `node:${version}`,
};

rule(dockerfile, () => "template.ejs", { async: true }, async function() {
  const [ source, version, type ] = this.name.match(dockerfile).slice(1);
  const template = await fs.readFile(path.join(__dirname, "template.ejs"), "utf8");
  await fs.ensureDir(path.dirname(path.join(__dirname, this.name)));
  await fs.writeFile(path.join(__dirname, this.name), ejs.render( template, {
    source,
    FROM: FROM[source](version),
    standard: true,
    full: type === "full",
  }));
});

task("default", [
  "alpine-latest-standard/Dockerfile",
  "alpine-latest-full/Dockerfile",
  "jessie-latest-standard/Dockerfile",
  "jessie-latest-full/Dockerfile",
  "alpine-8-standard/Dockerfile",
  "alpine-8-full/Dockerfile",
  "jessie-8-standard/Dockerfile",
  "jessie-8-full/Dockerfile",
], { parallelLimit: Infinity }, function(params) {
  console.log("Built all Dockerfiles");
});
