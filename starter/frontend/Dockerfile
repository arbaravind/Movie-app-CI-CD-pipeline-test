FROM  public.ecr.aws/docker/library/node:18.14.2-alpine3.17

ARG REACT_APP_MOVIE_API_URL
# ENV REACT_APP_MOVIE_API_URL=${REACT_APP_MOVIE_API_URL}
# ENV REACT_APP_MOVIE_API_URL="http://aeb9614cc4f1c4751adc97420a70524b-784435929.us-east-1.elb.amazonaws.com"
ENV REACT_APP_MOVIE_API_URL=$REACT_APP_MOVIE_API_URL

WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install packages
RUN npm ci

# Copy code
COPY . .

# Build the app
RUN npm run build

# Expose the port used by the React app
EXPOSE 3000

# Start the React app when the container starts
CMD ["npm", "run", "serve"]