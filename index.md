---
title:  Cluster Builder
---
<div id="title-flash">Automating the Creation of <span id="title-cluster-type">Kubernetes</span> Clusters in <span id="title-vmware-env">VMware ESXi</span> Environments</div>

---

Using freely available tools and only an annotated Ansible inventory file [cluster-builder](https://github.com/ids/cluster-builder) enables the configuration and deployment of fleets of VMware VMs to ESXi and Fusion hypervisors.

---

> One command... and the cluster is deployed!

<script src="https://asciinema.org/a/h32J527aKzUHHedqDA6KlQn0F.js" id="asciicast-h32J527aKzUHHedqDA6KlQn0F" async data-autoplay="true" data-size="small" data-speed="10"></script>
<script
  src="https://code.jquery.com/jquery-3.3.1.min.js"
  integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
  crossorigin="anonymous"></script>

__Cluster Builder__ is a unique toolset that can deploy _the identical cluster VM images used for production_ to local VMware Fusion development workstations for both the _operations_ and _development_ teams alike.  This enables both advanced local stack development, as well as meta orchestration cluster development, accelerating all development workflows on a shared codebase.  Clusters can be deployed and re-deployed locally, _and_ into production, _in minutes!_

__Cluster Builder__ follows an [immutable infrastructure](https://www.digitalocean.com/community/tutorials/what-is-immutable-infrastructure) philosophy even at the cluster node level.  Container orchestration clusters are defined in a simple text file and then deployed using a single command.  Always repeatable and documented, this single re-usable toolset can deploy numerous and varied orchestration clusters with a clear separation of configuration and deployment artifacts, while offering a mechanism for managing the various cluster definitions packages.

---
<div class="center">
<img style="width: 100px" src="/assets/images/cbLogo-100.png" >
<a id="try-cb-link" href="https://github.com/ids/cluster-builder">Try Cluster Builder</a>
</div>
---
<script>

window.onload = function() {

  function swapClusterType() {
    var cluster = $("#title-cluster-type").text();
    switch(cluster) {
      case "Kubernetes":
        cluster = "Docker Swarm";
        break;
      case "Docker Swarm":
        cluster = "DC/OS";
        break;
      default:
        cluster = "Kubernetes";
    }
    $("#title-cluster-type").fadeOut(function(){
      $("#title-cluster-type").html(cluster);
      $("#title-cluster-type").fadeIn();
    });
  }

  function swapEnv() {
    var cluster = $("#title-vmware-env").text();
    switch(cluster) {
      case "VMware ESXi":
        cluster = "VMware Fusion";
        break;
      default:
        cluster = "VMware ESXi";
    }
    $("#title-vmware-env").fadeOut(function(){
      $("#title-vmware-env").html(cluster);
      $("#title-vmware-env").fadeIn();
    });
  }

  setInterval(swapClusterType,5000);
  setInterval(swapEnv,3500);

  swapClusterType();
  swapEnv();

}

</script>

<style>

#title-flash {
  font-weight: 200;
  font-size: 1.5em;
}

#project_title,
#project_tagline {
  margin-left: 10px;
}

#title-cluster-type,
#title-vmware-env {
  font-weight: bolder;
  color: #333;
}

#try-cb-link {
  font-weight: 300;
  font-size: 1.5em;
}

.center {
  text-align: center;
}

.marketing-hype {
  color: #787977;
  font-weight: 400;
  font-size: 1.1em;
}

#main_content p {
  font-size: 1.1em;
  font-weight: 300;
  margin-top: 30px;
  margin-bottom: 30px;
}

</style>