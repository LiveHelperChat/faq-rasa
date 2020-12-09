# from rasa base image
FROM rasa/rasa:2.1.3
# copy all source and the Rasa generated model
COPY ./faq/ /app

# inform which port will run on
EXPOSE 5005

USER root

ENTRYPOINT []
ENV shell_mode false

RUN rasa train

# launch script (rasa shell or rasa run)
CMD sh -c 'if [ "$shell_mode" = false ]; then rasa run -p 5005 --cors "*"; else rasa shell -p 5005; fi'