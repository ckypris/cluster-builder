---
title:  Cluster Builder
---

Using freely available tools and only an annotated Ansible inventory file [cluster-builder](https://github.com/ids/cluster-builder) enables the configuration and deployment of fleets of container orchestration cluster VMs to VMware hypervisors, such as vSphere/ESXi, VMware Workstation Pro and VMware Fusion Pro.

> One command... and the cluster is deployed!

<script id="asciicast-AsUInfjr7c1hWgI5SmodVtd59" src="https://asciinema.org/a/AsUInfjr7c1hWgI5SmodVtd59.js" async data-autoplay="true" data-rows="41" data-theme="tango" data-size="small" data-speed="15"></script>

<script
  src="https://code.jquery.com/jquery-3.3.1.min.js"
  integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
  crossorigin="anonymous"></script>

__Cluster Builder__ is a Packer and Ansible based infrastructure as codebase that can deploy _identical cluster VM images in both local development and production VMware environments_, supporting both _operational_ and _development_ team workflows.  This enables advanced local stack development, as well as meta infrastructure orchestration cluster development.  Clusters can be deployed and re-deployed locally, _and_ into production, identically, _in minutes!_

__Cluster Builder__ follows an [immutable infrastructure](https://www.digitalocean.com/community/tutorials/what-is-immutable-infrastructure) philosophy even at the cluster node level.  Container orchestration clusters are defined in a simple text file and then deployed using a single command.  Always repeatable and documented, this re-usable framework can deploy numerous and varied orchestration clusters with a clear separation of configuration and deployment artifacts, while offering a mechanism for managing the resulting cluster definition packages.

__Cluster Builder__ can deploy the following container orchestration clusters:

* [Kubernetes](https://kubernetes.io/):
  * _Vanilla K8s_ `kubeadm` CentOS 7.6
  * _Vanilla K8s_ `kubeadm` Fedora  
* [DC/OS](https://dcos.io/) on CentOS 7.6
* [Docker Swarm CE (Community Edition)](https://docs.docker.com/engine/swarm/) on CentOS/RHEL 7.6.

__Cluster Builder__ can also deploy associated __Targetd Storage Appliance__ and __iSCSI Provisioners__ to provide backing persistent volume storage for K8s clusters.

> Hard to believe?  It's true.  Cluster Builder is a single infrastructure codebase that can automatically deploy all of the major container orchestration systems as production ready VMware VM clusters.  Not enough? It can also deploy the backing persistent volume technology to enable full stack containerized application deployment (_including the database_).  

__Cluster Builder__ utilizes _VMware_ and _Kubernetes_ as the on-premise datacenter components of a cost optimized _Hybrid Cloud strategy_. It's __fully open__, __forkable__ and __hackable__.  _Why start from scratch?_

---
<div class="center">
<img style="width: 100px" src="/assets/images/cbLogo2-100.png" >
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
      case "VMware Fusion":
        cluster = "VMware Workstation Windows";
        break;
      case "VMware Workstation Windows":
        cluster = "VMware Workstation Linux";
        break;
      default:
        cluster = "VMware ESXi";
    }
    $("#title-vmware-env").fadeOut(function(){
      $("#title-vmware-env").html(cluster);
      $("#title-vmware-env").fadeIn();
    });
  }

  //setInterval(swapClusterType,5000);
  //setInterval(swapEnv,3500);

  //swapClusterType();
  //swapEnv();

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

.asciicast {
  max-height: 511px;
}
</style>