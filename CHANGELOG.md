## Unreleased

### Added

- [PR #97](https://github.com/Orange-OpenSource/nifikop/pull/97) - **[Operator/NifiCluster]** Add ability to o define the maximum number of threads for timer driven processors available to the system.
- [PR #98](https://github.com/Orange-OpenSource/nifikop/pull/98) - **[Operator/NifiCluster]**  Add empty_dir volume for `/tmp` dir.

### Changed

### Deprecated

### Removed

### Fixed Bugs

## v0.6.0

### Added

- [PR #86](https://github.com/Orange-OpenSource/nifikop/pull/86) - **[Operator/Debugging]** Add events and improve HTTP calls error message
- [PR #87](https://github.com/Orange-OpenSource/nifikop/pull/87) - **[Operator/Configuration]** Allow to override the `.properties` files using a config map and/or a secret.
- [PR #87](https://github.com/Orange-OpenSource/nifikop/pull/87) - **[Operator/Configuration]** Allow to replace the `logback.xml` and `bootstrap_notification_service.xml` files using a config map or a secret.
- [PR #88](https://github.com/Orange-OpenSource/nifikop/pull/88) - **[Operator/Monitoring]** By choosing `prometheus` as type for an internal service in a NiFiCluster resource, the operator automatically creates the associated `reporting task`.

### Changed

- [PR #85](https://github.com/Orange-OpenSource/nifikop/pull/85) - **[Operator/Dependencies]** Upgrade cert-manager & operator sdk dependencies
- [PR #87](https://github.com/Orange-OpenSource/nifikop/pull/87) - **[Operator/Configuration]** The node configuration files are no more stored in a configmap, but in a secret.

### Deprecated

- [PR #85](https://github.com/Orange-OpenSource/nifikop/pull/85) - **[Operator/Finalizers]** The finalizer name format suggested by [Kubernetes docs](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/#finalizers) is <qualified-group>/<finalizer-name>, while the format previously documented by Operator SDK docs was <finalizer-name>.<qualified-group>. If your operator uses any finalizers with names matching the incorrect format, change them to match the official format. For example, finalizer.nifiusergroups.nifi.orange.com should be changed to nifiusergroups.nifi.orange.com/finalizer.

### Fixed Bugs

- [PR #87](https://github.com/Orange-OpenSource/nifikop/pull/87) - **[Operator/Configuration]** Since the v0.5.0 the operator doesn't catch certain resource changes, due to bad copy of resource, this issue avoid rolling upgrage trigger when some configuration changes.

## v0.5.3

### Fixed Bugs

- [PR #82](https://github.com/Orange-OpenSource/nifikop/pull/82) - **[Operator/NifiParameterContext]** Enable empty value
- [PR #83](https://github.com/Orange-OpenSource/nifikop/pull/83) - **[Operator/NiFiUser]** Rework the certificate secret creation, to prevent issues with JKS password creation.

## v0.5.2

### Fixed Bugs

- [PR #70](https://github.com/Orange-OpenSource/nifikop/pull/70) - **[Operator/NifiCluster]** Rework DNS names generation to fix non headless mode.

## v0.5.1

### Added

- [PR #61](https://github.com/Orange-OpenSource/nifikop/pull/61) - **[Operator/NifiCluster]** Replace hardcoded FSGroup (1000) with property (Implemented by @made-with-care in [PR #61](https://github.com/Orange-OpenSource/nifikop/pull/61))

### Fixed Bugs

- [PR #61](https://github.com/Orange-OpenSource/nifikop/pull/61) - **[Operator/NifiCluster]** Fix external service annotations (merge maps require a point for destination field)

## v0.5.0

### Added

- [PR #55](https://github.com/Orange-OpenSource/nifikop/pull/55) - **[Operator/NifiCluster]** Add the ability to define additional sidecar to each NiFi nodes.
- [PR #59](https://github.com/Orange-OpenSource/nifikop/pull/59) - **[Operator/NifiCluster]** Give the ability to define kubernetes services to expose the NiFi cluster.
- [PR #55](https://github.com/Orange-OpenSource/nifikop/pull/55) - **[Documentation]** Upgdrade to Docusaurus 2.0.0-alpha70 and enable versioned feature.

### Removed

- [PR #59](https://github.com/Orange-OpenSource/nifikop/pull/59) - **[Operator/NifiCluster]** No more default service to expose the NiFi cluster, you have to explicitly define ExternalService.

### Fixed Bugs

- [PR #62](https://github.com/Orange-OpenSource/nifikop/pull/62) - **[Operator/NifiCluster]** Fix DNS names for services in all-node mode.
- [PR #64](https://github.com/Orange-OpenSource/nifikop/pull/64) - **[Operator/NifiCluster]** Manage several NiFiClusters with the same managed user.

## v0.4.3

### Added

- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Operator/NifiUser]** Cert-manager integration can now be disabled (it's still required for secured cluster).

### Changed

- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Operator]** Upgrade operator-sdk from v0.18.0 to v.1.3.0, which upgrade k8s dependencies to 0.19.4 and migrate to Kubebuilder aligned project layout.
- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[CI]** Update steps with new Makefile commands.

### Deprecated

- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Operator/CRD]** No more support for Kubernetes cluster under version 1.16 (we no longer provide crds in version v1beta1)

### Fixed Bugs

- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Operator]** Upgrade k8s dependencies to match with new version requirement : [#52](https://github.com/Orange-OpenSource/nifikop/issues/52) [#51](https://github.com/Orange-OpenSource/nifikop/issues/51) [#33](https://github.com/Orange-OpenSource/nifikop/issues/33) 
- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Operator]** Fix the users used into Reader user group
- [PR #53](https://github.com/Orange-OpenSource/nifikop/pull/53) - **[Documentation]** Fix the chart version informations : [#51](https://github.com/Orange-OpenSource/nifikop/issues/51)

## v0.4.2-alpha-release

- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/42) - **[Operator]** Access policies enum type list

### Added

- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiUser]** Manage NiFi's users into NiFi Cluster
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiUserGroup]** Manage NiFi's user groups into NiFi Cluster
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator]** Manage NiFi's access policies
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiCluster]** Create three defaults groups : admins, readers, nodes
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiCluster]** Add pod disruption budget support


### Changed

- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Helm Chart]** Add CRDs
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiCluster]** Manage default process group id if not defined, using the root process group one.
- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiCluster]** Rename `zkAddresse` to `zkAddress`

### Removed

- [PR #41](https://github.com/Orange-OpenSource/nifikop/pull/41) - **[Operator/NifiCluster]** Remove `ClusterSecure` and `SiteToSiteSecure` by only checking if `SSLSecret` is set.


### Fixed Bugs

- [PR #30](https://github.com/Orange-OpenSource/nifikop/pull/40) - **[Documentation]** Fix getting started

## v0.3.1-release

### Fixed Bugs

- [PR #37](https://github.com/Orange-OpenSource/nifikop/pull/37) - **[Operator]** nifi.properties merge

## v0.3.0-release

### Added

- [PR #31](https://github.com/Orange-OpenSource/nifikop/pull/31) - **[Operator]** Dataflow lifecycle management

### Fixed Bugs

- [PR #30](https://github.com/Orange-OpenSource/nifikop/pull/30) - [Documentation] Fix slack link

## v0.2.1-release

### Added

- [PR #25](https://github.com/Orange-OpenSource/nifikop/pull/25) -  [Helm Chart] Add support for iterating over namespaces
- [PR #18](https://github.com/Orange-OpenSource/nifikop/pull/18) - [Operator] NiFiKop CRDs in version `v1beta1` of CustomResourceDefinition object.

### Changed

### Deprecated

### Removed

- [PR #18](https://github.com/Orange-OpenSource/nifikop/pull/18) - [Helm Chart] Remove CRDs deployment and append documentation.

### Fixed Bugs

- [PR #24](https://github.com/Orange-OpenSource/nifikop/pull/24) - [Documentation] Correct patterns & versions.
- [PR #28](https://github.com/Orange-OpenSource/nifikop/pull/28) - [Operator] PKI finalize bad namespace for ca cert.

## v0.2.0-release

### Added

- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Allow to override cluster domain
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Support external DNS
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Add `Spec.Service` field, allowing to add service's annotations.
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Add `Spec.Pod` field, allowing to add pod's annotations.
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Documentation & blog article about external dns and Let's encrypt usage.
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Documentation on RicKaaStley deployment.
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Improve test unit coverage.

### Changed

- [MR #17](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/17) - Upgrade dependencies
- [MR #17](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/17) - CRD generated under `apiextensions.k8s.io/v1`
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Set binami zookeeper helm chart as recommended solution for 
ZooKeeper.
- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Improve terraform setup for articles.
- [MR #18](https://gitlab.si.francetelecom.fr/kubernetes/nifikop/-/merge_requests/18) - Add ability to define if cert-manager is cluster scoped or not.
- [MR #18](https://gitlab.si.francetelecom.fr/kubernetes/nifikop/-/merge_requests/18) - Open source changes

### Deprecated

- [MR #16](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/16) - Change `Spec.HeadlessServiceEnabled` to`Spec.Service.HeadlessEnabled`

### Removed

### Fixed Bugs

- [MR #13](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/13) - Fix scale out init scope in TLS cluster.

## v0.1.0-release

### Added

- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Implement TLS certificates creation with Cert-Manager
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Add NifiUser custom resource for TLS users (nodes and operator)
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Implement NifiUser and TLS reconciliation, with secrets injection
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Add Initial Admin definition into NifCluster
- [MR #9](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/9) - Add NigoApi dependency
- [MR #9](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/9) - Implement HTTP Client wrapper for Operator
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Implement multi-namespace watch logic
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Documentation & tutorial on OpenId Connect configuration

### Changed

- [MR #9](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/9) - Improve rolling upgrade : on ready pods, not just running
- [MR #9](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/9) - Improve cluster task events filter
- [MR #9](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/9) - Improve Helm publication removing the cache
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Move secure cluster configuration level (at Spec level)
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - Move repo reference to the GitLab one

### Deprecated

### Removed

### Fixed Bugs

- [MR #7](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/7) - Decommission lifecycle on Coordinator node
- [MR #10](https://github.com/Orange-OpenSource/nifikop/-/merge_requests/10) - HTTPS port selection

## v0.0.1-release

### Added

- Implement pod management lifecycle
- Implement Graceful downscale pod lifecycle management
- Implement Graceful upscale pod lifecycle management
- Implement configuration lifecycle management for : nifi.properties, zookeeper.properties, state-management.xml, login-identity-providers.xml, logback.xml, bootstrap.conf, bootstrap-notification-servces.xml
- Initiate documentations
- Implementation basic makefile for some actions (debug, build, deploy, run, push, unit-test)
- Create helm chart for operator
- Add Documentation for internal deployment
- Add Gitlab CI Pipeline

### Changed

### Deprecated

### Removed

### Fixed Bugs