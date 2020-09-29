# Command line options
AddOption('--all',
          dest='build_config',
          action='store_const',
          const='all',
          help='Build both debug and release configurations',
)
AddOption('--release',
          dest='build_config',
          action='store_const',
          const='release',
          help='Build the release configuration',
)

# Build configurations
configurations = [
    {
        'name': 'debug',
        'optimization_flags': [
            '-Og',
            '-g',
        ],
    },
    {
        'name': 'release',
        'optimization_flags': [
            '-O2',
        ],
    },
]

selected_config = GetOption('build_config') or 'debug'

for build_config in configurations:
    if selected_config == build_config['name'] or selected_config == 'all':
        SConscript('projects/STM32L496-Discovery/GCC/SConscript',
                   exports=['build_config'])
