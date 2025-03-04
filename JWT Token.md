The JWT claims differ from those generated once the token is fed to the API.

The issue is not with token generation, but the claims are transformed once the token is passed to the API.

The following snip-it of code in the `Program.cs` file can fix this: 

`JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear(); // important`
`JwtSecurityTokenHandler.DefaultOutboundClaimTypeMap.Clear(); //important`

`builder.Services`
    `.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)`
    `.AddJwtBearer(options =>`
    `{`
        `options.TokenValidationParameters = new TokenValidationParameters`
        `{`
            `ValidateIssuer = true,`
            `ValidateAudience = true,`
            `ValidateLifetime = true,`
            `ValidateIssuerSigningKey = true,`
            `ValidIssuer = builder.Configuration["Jwt:Issuer"],`
            `ValidAudience = builder.Configuration["Jwt:Audience"],`
            `IssuerSigningKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(builder.Configuration["Jwt:Key"]))`
        `};`

        `options.MapInboundClaims = false; // Important!`
    `});`

`

