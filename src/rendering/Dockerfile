# escape=`

#
# Development-only image for running Next.js in a containerized environment.
# Assumes that the Next.js rendering host source is mounted to c:\app.
#

ARG PARENT_IMAGE
FROM ${PARENT_IMAGE} as deps
WORKDIR /app
COPY . .
#COPY package.json ./
#RUN DIR
#RUN npm install -g npm@9.8.1
#RUN npm cache clean
#RUN npm config set update-notifier false
#RUN npm install --silent

#FROM ${PARENT_IMAGE} as builder
#WORKDIR /app
#COPY . .
RUN DIR
#COPY --from=deps /app/node_modules ./node_modules
#ENV NEXT_TELEMETRY_DISABLED 1
#RUN npm run build --silent

#FROM ${PARENT_IMAGE} as runner
#WORKDIR /app
#ENV NODE_ENV production
#ENV NEXT_TELEMETRY_DISABLED 1
#USER ContainerAdministrator

#SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

#COPY --from=builder /app/next.config.js ./next.config.js
#COPY --from=builder /app/scjssconfig.json ./scjssconfig.json
#COPY --from=builder /app/tsconfig.scripts.json ./tsconfig.scripts.json
##COPY --from=builder /app/tsconfig.json ./tsconfig.json
#COPY --from=builder /app/public ./public
#COPY --from=builder /app/.next ./.next
#COPY --from=builder /app/node_modules ./node_modules
#COPY --from=builder /app/scripts ./scripts
#COPY --from=builder /app/src ./src
#COPY --from=builder /app/package.json ./package.json
#COPY --from=builder /app/.graphql-let.yml ./.graphql-let.yml


#RUN Remove-Item -Path C:\app\.next\static -Force -Recurse;

EXPOSE 80
EXPOSE 443
EXPOSE 8089
EXPOSE 3005
EXPOSE 3000
ENTRYPOINT "npm run start"