package(default_visibility = ["//visibility:public"])

cc_library(
    name="Collision",
    includes = [
        ".",
        "BulletCollision/BroadPhaseCollision",
    ],

    hdrs = glob([
        "btBulletCollisionCommon.h",
        "BulletCollision/**/*.h",
        "BulletCollision/**/*.cpp",
        #'BulletCollision/CollisionDispatch/btCollisionWorld.h',
        #"**/*.h",
    ]),
    srcs = [
        "btBulletCollisionAll.cpp",
    ],
    deps = [
        ":LinearMath",
    ],
    )

cc_library(
    name="Dynamics",
    hdrs = glob([
        "btBulletDynamicsCommon.h",
        "BulletDynamics/**/*.h",
        "BulletDynamics/**/*.cpp",
        ]),
    srcs = [
        "btBulletDynamicsAll.cpp",
        ],
    includes = [
        ".",
        ],
    deps = [
        ":Collision",
        ],
    )

cc_library(
    name="LinearMath",
    hdrs = glob([
        "LinearMath/**/*.h",
        "LinearMath/**/*.cpp",
    ]),
    srcs = [
        "btLinearMathAll.cpp",
    ],
    includes = [
        ".",
    ],
    )
