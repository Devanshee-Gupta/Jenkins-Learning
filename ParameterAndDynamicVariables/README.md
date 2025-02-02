# Parameters and Dynamic variables -

## Dynamic variables -
Dynamic variables allows to generate or compute values during the pipeline execution, rather than hard-coding them.

## Parameters-
The parameters directive provides a list of parameters that a user should provide when triggering the Pipeline. The values for these user-specified parameters are made available to Pipeline steps via the params object.
    
    
    Available Parameters-
    1. string 
    A parameter of a string type, 
    for example: parameters { string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: '') }.

    2. text
    A text parameter, which can contain multiple lines, 
    for example: parameters { text(name: 'DEPLOY_TEXT', defaultValue: 'One\nTwo\nThree\n', description: '') }.

    3. booleanParam
    A boolean parameter, 
    for example: parameters { booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '') }.

    4. choice 
    A choice parameter, 
    for example: parameters { choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '') }. 
    The first value is the default.

    5. password
    A password parameter, 
    for example: parameters { password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'A secret password') }.
    

  Access value of parameter (from params object) - ${params.parameter_name} like for example, ${params.DEPLOY_ENV}
