load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "com_googlesource_gerrit_bazlets",
    remote = "https://gerrit.googlesource.com/bazlets",
    commit = "968b97fa03a9d2afd760f2e8ede3d5643da390d2",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "4.1"
RULES_JVM_EXTERNAL_SHA = "f36441aa876c4f6427bfb2d1f2d723b48e9d930b62662bf723ddfb8fc80f0140"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "com.google.code.gson:gson:2.8.9",
        "org.junit.jupiter:junit-jupiter-api:5.8.1",
    ],
    fetch_sources = True,
    repositories = [
        # Private repositories are supported through HTTP Basic auth
        # "http://username:password@localhost:8081/artifactory/my-repository",
        # "https://maven.google.com",
        "http://uk.maven.org/maven2",
        "https://jcenter.bintray.com/",
    ],
)

