package(default_visibility = ["//visibility:public"])

defines = [
    # TODO: change this for production
    "CMAKE_BUILD_TYPE=Debug", 
    ] + select({
        "//platforms:win32": [
            "_WIN32", 
            "USE_DOUBLE_PRECISION=ON", 
            "BT_USE_SSE", 
            "BT_USE_SSE_IN_API", 
            "BT_USE_SIMD_VECTOR3", 
            ],
        "//conditions:default": [ ],
    })

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
    defines = defines)

cc_library(
    name="Dynamics",
    hdrs = [ "btBulletDynamicsCommon.h", ] + glob([
          "BulletDynamics/**/*.h",
        ]),
    srcs = [
        "btBulletDynamicsAll.cpp",
        ] + glob([
          "BulletDynamics/**/*.cpp",
        ]),
    includes = [
        ".",
    ],
    deps = [
        ":Collision",
        ],
    defines = defines)

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
    defines = defines)
