project('networkz', 'cpp')

src = [
    'src/common/platform.hh',
    'src/common/defer.hh',
    'src/common/precompiled.hh', 'src/common/precompiled.cc',

    'src/render/imgui/opengl.hh', 'src/render/imgui/opengl.cc',
    'src/render/imgui/platform.hh','src/render/imgui/platform.cc',


    'src/render/render.hh',
    'src/render/init.cc',
    'src/render/loop.cc',

    'src/main.cc',

    # imgui
    'external/imgui/imgui.cpp', 'external/imgui/imgui_draw.cpp', 'external/imgui/imgui_widgets.cpp', 'external/imgui/imgui_demo.cpp'
]

includes = include_directories(['src/', 'external/imgui'])

deps = []

args = ['--bind', '-s', 'USE_SDL=2', '-s', 'USE_WEBGL2=1', '-s', 'FULL_ES3=1', '-s', 'ASSERTIONS=1']

executable('networkz', src, 
           include_directories : includes,
           cpp_pch: 'src/common/precompiled.hh',
           dependencies: deps,
           name_suffix: 'js',
           cpp_args: args,
           link_args: args)

# Configure index.html
conf_data = configuration_data()
conf_data.set('exe_name', 'networkz')
configure_file(input : 'dist/index.html',
               output : 'index.html',
               configuration : conf_data)