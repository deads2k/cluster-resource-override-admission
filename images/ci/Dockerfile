FROM registry.svc.ci.openshift.org/openshift/release:golang-1.15 AS builder

WORKDIR /go/src/github.com/openshift/cluster-resource-override-admission

COPY . .

RUN make build

FROM registry.svc.ci.openshift.org/openshift/origin-v4.0:base

COPY --from=builder /go/src/github.com/openshift/cluster-resource-override-admission/bin/cluster-resource-override-admission /usr/bin/

